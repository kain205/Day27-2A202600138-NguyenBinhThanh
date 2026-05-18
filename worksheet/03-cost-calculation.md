# 03 · Cost Calculation — Tính chi phí từng Config × 2 Scenarios

> **Mục tiêu**: Với mỗi config đã thiết kế ở `02-config-design.md`, tính cost/turn → cost/conversation → monthly cho cả 2 scenarios (low season + high season).
>
> **Thời gian**: 55 phút (phần lớn của Main phase) — checkpoint 11:00 và 11:20

---

## Cách làm

**Đừng tính tay từng turn — đó là cách thừa thời gian.** Dùng AI để tính. Dán prompt template từ `prompts/01-cost-calc.md` vào ChatGPT/Claude/Gemini, thay parameters theo config của nhóm, AI sẽ tính cho.

Tuy nhiên nhóm phải **hiểu** kết quả AI trả về, không phải copy-paste mù. Mỗi lần AI trả số, nhóm phải tự kiểm 1 lần: con số này có hợp lý không? Có vẻ quá đắt hay quá rẻ?

---

## Trước khi gọi AI — Setup chung

**Các tham số cố định cho tất cả configs** (tham khảo `cost-reference-card.md` mục 4):

```text
System prompt:              500 tokens
User message:                80 tokens
Assistant response:         180 tokens (output)
1 prior turn (history):     260 tokens (80 user + 180 assistant)
RAG top-5 chunks:         1,250 tokens (cố định)
Web search results:         800 tokens (khi bật)
Web search API call:       $0.008 / call (Tavily)
LLM classifier:            ~170 tokens (150 in + 20 out) — nếu dùng
```

**Scenario A — mùa thấp điểm**:

```text
Volume:            300 conversations / ngày
Turns/conv:        avg 4 lượt
Intent mix:        Guide 50%, Visa 25%, Weather 10%, Booking 10%, Complaint 5%
AI-served ratio:   85% (15% là Booking + Complaint = handoff)
```

**Scenario B — mùa cao điểm**:

```text
Volume:           1,200 conversations / ngày (×4)
Turns/conv:        avg 7 lượt
Intent mix:        Guide 30%, Visa 15%, Weather 10%, Booking 35%, Complaint 10%
AI-served ratio:   55% (45% là handoff)
```

**Human baseline để so sánh**: $0.50 / conversation cố định.

---

## Quy trình tính cho 1 config (lặp lại cho từng config)

### Bước 1 — Cost per turn (4 mốc: Turn 1, 3, 5, 7)

Với mỗi mốc, tính:

1. **History tokens** = (T − 1) × 260 nếu Full · min(T−1, N) × 260 nếu Last N
2. **Input total** = 500 (sys) + history + 1,250 (RAG) + (800 nếu web ON cho intent này) + 80 (msg)
3. **Output** = 180 tokens
4. **Cost model** = (input × $/M_input + output × $/M_output) / 1,000,000
5. **Cost web API** = $0.008 nếu web ON cho intent này, ngược lại $0
6. **Total cost/turn** = cost model + cost web

### Bước 2 — Cost per conversation cho từng intent

- Scenario A: cộng cost của Turn 1 → Turn 4 (4 turns)
- Scenario B: cộng cost của Turn 1 → Turn 7 (7 turns)

### Bước 3 — Weighted average cost per conversation

**Scenario A** (Guide 50%, Visa 25%, Weather 10%, Booking 10%, Complaint 5%):

```text
avg_cost_A = 50% × cost_conv_guide_4t
          + 25% × cost_conv_visa_4t
          + 10% × cost_conv_weather_4t
          + 15% × $0 (handoff)
```

**Scenario B** (Guide 30%, Visa 15%, Weather 10%, Booking 35%, Complaint 10%):

```text
avg_cost_B = 30% × cost_conv_guide_7t
          + 15% × cost_conv_visa_7t
          + 10% × cost_conv_weather_7t
          + 45% × $0 (handoff)
```

### Bước 4 — Monthly cost

```text
monthly_A = avg_cost_A × 300 conv/ngày × 30 ngày
monthly_B = avg_cost_B × 1,200 conv/ngày × 30 ngày
```

### Bước 5 — So sánh với human baseline

```text
human_A = $0.50 × 300 × 30 = $4,500 / tháng
human_B = $0.50 × 1,200 × 30 = $18,000 / tháng
```

---

## Điền số cho từng config

### Config 1 — Economy Mode

**Config parameters:** GPT-4o-mini ($0.15/$0.60 per 1M) · Web OFF · History Last 3 · Classifier keyword ($0)

**Bảng cost per turn — Guide intent (web OFF, Last 3):**

| Turn | History tokens | Input total | Output | Cost model | Cost web | Total/turn |
|---|---|---|---|---|---|---|
| T1 | 0 | 1,830 | 180 | $0.000383 | $0 | $0.000383 |
| T2 | 260 | 2,090 | 180 | $0.000422 | $0 | $0.000422 |
| T3 | 520 | 2,350 | 180 | $0.000461 | $0 | $0.000461 |
| T4 | 780 | 2,610 | 180 | $0.000500 | $0 | $0.000500 |
| T5 | 780* | 2,610 | 180 | $0.000500 | $0 | $0.000500 |
| T6 | 780* | 2,610 | 180 | $0.000500 | $0 | $0.000500 |
| T7 | 780* | 2,610 | 180 | $0.000500 | $0 | $0.000500 |

*Last 3: history = min(T−1, 3) × 260. Từ T4 trở đi cố định 780 tokens.

Công thức T1: input = 500 + 0 + 1,250 + 80 = 1,830; cost = (1,830×0.15 + 180×0.60)/1,000,000 = $0.000383
Công thức T4: input = 500 + 780 + 1,250 + 80 = 2,610; cost = (2,610×0.15 + 180×0.60)/1,000,000 = $0.000500

**Cost per conversation — từng intent:**

| Intent | Scenario A (4 turns) | Scenario B (7 turns) | Ghi chú |
|---|---|---|---|
| Guide | $0.001764 | $0.003263 | Web OFF, GPT-4o-mini |
| Visa | $0.001764 | $0.003263 | Web OFF (Economy tắt hết) |
| Weather | $0.001764 | $0.003263 | Web OFF |
| Booking/Complaint | $0 | $0 | Handoff — $0 LLM |

*Visa và Guide giống nhau vì Economy Mode tắt web search toàn bộ.*

**Weighted average cost per conversation:**

```text
Scenario A:
avg_cost_A = 50% × $0.001764 + 25% × $0.001764 + 10% × $0.001764 + 15% × $0
           = 85% × $0.001764 = $0.001499 / conversation

Scenario B:
avg_cost_B = 30% × $0.003263 + 15% × $0.003263 + 10% × $0.003263 + 45% × $0
           = 55% × $0.003263 = $0.001795 / conversation
```

| Item | Scenario A (4 turns) | Scenario B (7 turns) |
|---|---|---|
| Cost / conversation (avg) | $0.001499 | $0.001795 |
| Monthly cost | $13.49 | $64.62 |
| Human baseline | $4,500 | $18,000 |
| **Rẻ hơn human** | **334×** | **279×** |
| **Savings %** | **99.7%** | **99.6%** |

**Sanity check**:

```text
Cost/conv $0.0015–$0.0018 hợp lý cho cheap model + no web search — đây là mức lý thuyết tối thiểu.
Monthly A $13.49 và Monthly B $64.62 — có vẻ rất rẻ nhưng đúng: GPT-4o-mini cực rẻ,
web OFF, history short → tổng token per turn thấp.
Cảnh báo: rẻ không đồng nghĩa là không có rủi ro — visa info outdated là real risk.
```

---

### Config 2 — VIP Concierge

**Config parameters:** Claude Sonnet 4.6 ($3.00/$15.00 per 1M) · Web ON selective (Visa + Weather, mọi turn) · History Full · Classifier keyword ($0)

**Bảng cost per turn — Visa intent (web ON every turn, Full history):**

| Turn | History tokens | Input total | Output | Cost model | Cost web | Total/turn |
|---|---|---|---|---|---|---|
| T1 | 0 | 2,630 | 180 | $0.010590 | $0.008 | $0.018590 |
| T2 | 260 | 2,890 | 180 | $0.011370 | $0.008 | $0.019370 |
| T3 | 520 | 3,150 | 180 | $0.012150 | $0.008 | $0.020150 |
| T4 | 780 | 3,410 | 180 | $0.012930 | $0.008 | $0.020930 |
| T5 | 1,040 | 3,670 | 180 | $0.013710 | $0.008 | $0.021710 |
| T6 | 1,300 | 3,930 | 180 | $0.014490 | $0.008 | $0.022490 |
| T7 | 1,560 | 4,190 | 180 | $0.015270 | $0.008 | $0.023270 |

Full history: history = (T−1) × 260. Input (web ON) = 500 + history + 1,250 + 800 + 80.
Công thức T7: input = 500 + 1,560 + 1,250 + 800 + 80 = 4,190; cost_model = (4,190×3.00 + 180×15.00)/1M = $0.015270

**Cost per conversation — từng intent:**

| Intent | Scenario A (4 turns) | Scenario B (7 turns) | Ghi chú |
|---|---|---|---|
| Guide | $0.037440 | $0.073710 | Web OFF, Sonnet |
| Visa | $0.079040 | $0.146510 | Web ON mọi turn ($0.008×4/7), Sonnet |
| Weather | $0.079040 | $0.146510 | Web ON mọi turn, Sonnet |
| Booking/Complaint | $0 | $0 | Handoff |

**Weighted average cost per conversation:**

```text
Scenario A:
avg_cost_A = 50% × $0.037440 + 25% × $0.079040 + 10% × $0.079040 + 15% × $0
           = $0.018720 + $0.019760 + $0.007904
           = $0.046384 / conversation

Scenario B:
avg_cost_B = 30% × $0.073710 + 15% × $0.146510 + 10% × $0.146510 + 45% × $0
           = $0.022113 + $0.021977 + $0.014651
           = $0.058741 / conversation
```

| Item | Scenario A | Scenario B |
|---|---|---|
| Cost / conversation (avg) | $0.046384 | $0.058741 |
| Monthly cost | $417.46 | $2,114.68 |
| Human baseline | $4,500 | $18,000 |
| **Rẻ hơn human** | **10.8×** | **8.5×** |
| **Savings %** | **90.7%** | **88.3%** |

**Sanity check**:

```text
Cost/conv $0.046–$0.059 hợp lý cho Sonnet (strong model) + web ON + Full history.
So với Economy Mode: đắt gấp ~31× cho Scenario A, ~33× cho Scenario B.
Monthly B $2,114 vẫn rẻ hơn human $18,000 khoảng 8.5× — justify được cho khách VIP.
Lưu ý: web API $0.008/call cao hơn $0.005 trong ví dụ mẫu — dùng giá Tavily chính xác.
```

---

### Config 3 — Smart Balance

**Config parameters:**
- Guide/Weather response: GPT-4o-mini ($0.15/$0.60 per 1M)
- Visa response: Claude Haiku 4.5 ($1.00/$5.00 per 1M)
- Web: ON selective (Visa + Weather, mọi turn của 2 intent này)
- History: Last 5
- Classifier: keyword ($0)

**Bảng cost per turn — Visa intent (web ON, Last 5, Claude Haiku 4.5):**

| Turn | History tokens | Input total | Output | Cost model | Cost web | Total/turn |
|---|---|---|---|---|---|---|
| T1 | 0 | 2,630 | 180 | $0.003530 | $0.008 | $0.011530 |
| T2 | 260 | 2,890 | 180 | $0.003790 | $0.008 | $0.011790 |
| T3 | 520 | 3,150 | 180 | $0.004050 | $0.008 | $0.012050 |
| T4 | 780 | 3,410 | 180 | $0.004310 | $0.008 | $0.012310 |
| T5 | 1,040 | 3,670 | 180 | $0.004570 | $0.008 | $0.012570 |
| T6 | 1,300 | 3,930 | 180 | $0.004830 | $0.008 | $0.012830 |
| T7 | 1,300* | 3,930 | 180 | $0.004830 | $0.008 | $0.012830 |

*Last 5: history = min(T−1, 5) × 260. T6 trở đi cố định 1,300 tokens.

**Bảng cost per turn — Weather intent (web ON, Last 5, GPT-4o-mini):**

| Turn | History tokens | Input total | Output | Cost model | Cost web | Total/turn |
|---|---|---|---|---|---|---|
| T1 | 0 | 2,630 | 180 | $0.000503 | $0.008 | $0.008503 |
| T2 | 260 | 2,890 | 180 | $0.000542 | $0.008 | $0.008542 |
| T3 | 520 | 3,150 | 180 | $0.000581 | $0.008 | $0.008581 |
| T4 | 780 | 3,410 | 180 | $0.000620 | $0.008 | $0.008620 |
| T5 | 1,040 | 3,670 | 180 | $0.000659 | $0.008 | $0.008659 |
| T6 | 1,300 | 3,930 | 180 | $0.000698 | $0.008 | $0.008698 |
| T7 | 1,300* | 3,930 | 180 | $0.000698 | $0.008 | $0.008698 |

**Cost per conversation — từng intent:**

| Intent | Scenario A (4 turns) | Scenario B (7 turns) | Model dùng |
|---|---|---|---|
| Guide | $0.001764 | $0.003458 | GPT-4o-mini, web OFF |
| Visa | $0.047680 | $0.085910 | Haiku 4.5, web ON ($0.008×turn) |
| Weather | $0.034246 | $0.059901 | GPT-4o-mini, web ON |
| Booking/Complaint | $0 | $0 | Handoff |

**Weighted average cost per conversation:**

```text
Scenario A:
avg_cost_A = 50% × $0.001764 + 25% × $0.047680 + 10% × $0.034246 + 15% × $0
           = $0.000882 + $0.011920 + $0.003425
           = $0.016227 / conversation

Scenario B:
avg_cost_B = 30% × $0.003458 + 15% × $0.085910 + 10% × $0.059901 + 45% × $0
           = $0.001037 + $0.012887 + $0.005990
           = $0.019914 / conversation
```

| Item | Scenario A | Scenario B |
|---|---|---|
| Cost / conversation (avg) | $0.016227 | $0.019914 |
| Monthly cost | $146.04 | $717.90 |
| Human baseline | $4,500 | $18,000 |
| **Rẻ hơn human** | **30.8×** | **25.1×** |
| **Savings %** | **96.8%** | **96.0%** |

**Sanity check**:

```text
Cost/conv $0.016–$0.020 hợp lý — nằm giữa Economy ($0.0015) và VIP Concierge ($0.046–$0.059).
Visa conv là khoản tốn nhất vì Haiku + web search mỗi turn ($0.008 × 4 turns = $0.032 chỉ web API).
Scenario B đắt hơn Scenario A khoảng 4.9× dù volume tăng 4× — vì Booking 35% + Complaint 10% = $0
kéo average down mạnh ở Scenario B. Hoàn toàn hợp lý.
```

---

### Config 4 (optional) — Google Lite

**Config parameters:** Gemini 2.5 Flash-Lite ($0.10/$0.40 per 1M) · Web ON selective (Visa + Weather) · History Last 5 · Classifier keyword ($0)

**Cost per conversation — ước tính nhanh:**

Guide 4 turns (web OFF, Last 5, Gemini Flash-Lite): ~$0.000253/turn average → $0.001150/conv
Visa 4 turns (web ON, Last 5): model rẻ + $0.008×4 web → ~$0.033285/conv
Weather 4 turns (web ON): tương tự Visa về web cost → ~$0.033285/conv

```text
avg_cost_A ≈ 50%×$0.001150 + 25%×$0.033285 + 10%×$0.033285 + 15%×$0
           ≈ $0.000575 + $0.008321 + $0.003329
           ≈ $0.012225 / conversation

Monthly A ≈ $0.012225 × 9,000 ≈ $110.03
Monthly B ≈ $0.014700 × 36,000 ≈ $529.20
```

| Item | Scenario A | Scenario B |
|---|---|---|
| Cost / conversation (avg) | ~$0.012225 | ~$0.014700 |
| Monthly cost | ~$110.03 | ~$529.20 |
| **Rẻ hơn human** | **~40.8×** | **~34.0×** |
| **Savings %** | **~97.6%** | **~97.1%** |

*Config 4 gần tương đương Smart Balance về cost nhưng dùng 1 model duy nhất (đơn giản hơn về routing).*
*Tradeoff: Gemini Flash-Lite quality thấp hơn Haiku 4.5 cho visa accuracy.*

---

## Quality + Speed estimate (qualitative)

| Config | Quality (Low/Med/High) | Speed (Low/Med/High) | Lý do |
|---|---|---|---|
| 1: Economy Mode | Low–Med | High | GPT-4o-mini nhanh (~200ms), web OFF ít latency; visa outdated risk kéo quality xuống |
| 2: VIP Concierge | High | Low–Med | Sonnet strong quality; web ON + full context dài → +2–3s latency mỗi turn |
| 3: Smart Balance | Med–High | Med | Haiku cho visa đủ chính xác; GPT-4o-mini cho FAQ nhanh; web ON selective thêm ~1s |
| 4: Google Lite | Med | High | Gemini Flash-Lite rất nhanh; web ON bù visa freshness; quality hơi thấp hơn Smart Balance |

---

## Bảng kiểm trước khi sang file tiếp theo

- [x] Tất cả ≥3 configs đã có cost/conv + monthly cho cả 2 scenarios
- [x] Đã so sánh từng config với human baseline ($0.50/conv)
- [x] Có quality + speed estimate cho mỗi config
- [x] Đã sanity check — không có số "quá lạ"

⚑ **Checkpoint 11:00**: ≥1 config đã tính cost xong &nbsp; · &nbsp; ⚑ **Checkpoint 11:20**: tất cả configs đã tính cost xong cho cả 2 scenarios.

Xong → mở `04-comparison-table.md`.
