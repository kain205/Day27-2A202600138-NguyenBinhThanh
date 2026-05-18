# 04 · Comparison Table — Bảng so sánh đầy đủ

> **Mục tiêu**: Tổng hợp tất cả số đã tính ở `03-cost-calculation.md` thành 1 bảng so sánh duy nhất — đây là artifact chính nhóm sẽ present.
>
> **Thời gian**: 10 phút (đầu phần Final)

---

## Vì sao có bảng so sánh?

Khi sếp hỏi "Nên deploy config nào?", bạn cần đặt lên bàn **1 bảng** thay vì đọc 3 báo cáo riêng. Bảng so sánh đầy đủ cho phép so sánh thẳng từng dòng, dễ nhìn ra tradeoff.

---

## Bảng chính

| | Config 1 | Config 2 | Config 3 | Config 4 |
|---|---|---|---|---|
| **Tên** | Economy Mode | VIP Concierge | Smart Balance | Google Lite |
| **① Model** | GPT-4o-mini (all intents) | Claude Sonnet 4.6 (all intents) | GPT-4o-mini (Guide/Weather) + Haiku 4.5 (Visa) | Gemini 2.5 Flash-Lite (all intents) |
| **② Web search** | OFF | ON selective (Visa + Weather) | ON selective (Visa + Weather) | ON selective (Visa + Weather) |
| **③ History** | Last 3 | Full | Last 5 | Last 5 |
| **Intent classifier** | Keyword | Keyword | Keyword | Keyword |
| **Cost / conv (Scenario A — 4 turns)** | $0.0015 | $0.0464 | $0.0162 | ~$0.0122 |
| **Cost / conv (Scenario B — 7 turns)** | $0.0018 | $0.0587 | $0.0199 | ~$0.0147 |
| **Monthly A** (300 conv/day × 30) | $13.49 | $417.46 | $146.04 | ~$110.03 |
| **Monthly B** (1,200 conv/day × 30) | $64.62 | $2,114.68 | $717.90 | ~$529.20 |
| **vs human $4,500/mo (A)** | rẻ **334×** | rẻ **10.8×** | rẻ **30.8×** | rẻ **~40.8×** |
| **vs human $18,000/mo (B)** | rẻ **279×** | rẻ **8.5×** | rẻ **25.1×** | rẻ **~34.0×** |
| **Savings % (A)** | **99.7%** | **90.7%** | **96.8%** | **~97.6%** |
| **Savings % (B)** | **99.6%** | **88.3%** | **96.0%** | **~97.1%** |
| **Quality estimate** | Low–Med | High | Med–High | Med |
| **Speed estimate** | High | Low–Med | Med | High |
| **Điểm yếu chính** | Visa info outdated (web OFF); context loss sau turn 3 | Cost spike Scenario B ($2,115/tháng); latency cao (~3–5s) | Routing phức tạp — cần classify đúng intent để gọi đúng model | Gemini Flash-Lite quality thấp hơn Haiku cho visa accuracy |
| **Best for** | Mùa thấp điểm, khách hỏi Guide FAQ đơn giản, budget bị siết | Khách VIP mùa cao điểm, tour cao cấp cần tư vấn chính xác | Mọi mùa — balance tốt nhất giữa cost/quality/risk | Startup muốn thử Google provider, cost thấp + web search |

---

## Quan sát nhanh từ bảng

Trước khi sang file recommendation, trả lời 4 câu — đây là material để present:

### Câu 1 — Config rẻ nhất là gì? Đắt nhất là gì?

```text
Rẻ nhất: Economy Mode — monthly B = $64.62
Đắt nhất: VIP Concierge — monthly B = $2,114.68
Chênh: 32.7× lần (nhưng Quality gap chỉ Low-Med vs High → mỗi bậc quality cost gấp ~5.7×)

So sánh thú vị: Smart Balance đắt hơn Economy Mode 11.1× nhưng có web search cho visa/weather
→ giảm risk sai thông tin đáng kể. VIP Concierge đắt hơn Smart Balance 2.9× nhưng quality
chỉ tăng 1 bậc (Med-High → High) → diminishing returns rõ ràng.
```

### Câu 2 — Knob nào ảnh hưởng cost nhiều nhất?

```text
① Model tier là knob ảnh hưởng lớn nhất:
   - GPT-4o-mini vs Sonnet 4.6: input price chênh 20× ($0.15 vs $3.00/1M)
   - Economy Mode vs VIP Concierge (cùng intent mix): Monthly B chênh $2,050 — phần lớn do model

② Web search ảnh hưởng đáng kể với model rẻ:
   - Với GPT-4o-mini: $0.008/call >> model cost (~$0.0005/turn) → web cost chiếm ~94% của turn
   - Kết quả: Economy Mode (web OFF) vs Smart Balance (web ON selective) — cost chênh 11× ở monthly
   - Nhưng với Sonnet: model cost là chủ đạo, web search chỉ thêm ~16% per turn

③ History ảnh hưởng nhỏ hơn:
   - Last 3 vs Full ở Scenario B (7 turns): Full thêm ~780 tokens history từ T4
   - Với Sonnet: mỗi 260 tokens thêm = $0.00078 input → 3 extra turns = $0.0023/turn
   - History quan trọng hơn khi dùng model mạnh và conversation dài
```

### Câu 3 — Tại sao Scenario B không đắt ×7 lần Scenario A?

```text
Volume Scenario B = ×4 lần Scenario A. Turns dài hơn (7 vs 4 = ×1.75). Mong đợi monthly B ≈ A × 7.
Thực tế: Economy Mode chỉ ~4.8× (64.62/13.49), Smart Balance ~4.9× (717.90/146.04).

Lý do chính: Intent mix Scenario B có Booking 35% + Complaint 10% = 45% handoff = $0 LLM.
Trong khi Scenario A chỉ có 15% handoff.

AI-served turns thực tế:
- Scenario A: 85% × 4 turns = 3.4 effective AI turns/conv
- Scenario B: 55% × 7 turns = 3.85 effective AI turns/conv (chỉ tăng 1.13×)
→ Volume tăng 4× × effective turns tăng 1.13× = 4.52× ≈ phù hợp với số thực (~4.8×)

Insight: Booking/Complaint cao ở Scenario B là "bộ giảm sốc" tự nhiên cho cost.
```

### Câu 4 — Có config nào AI đắt hơn human không?

```text
Không có config nào đắt hơn human — tất cả 4 configs đều rẻ hơn đáng kể.
Rẻ nhất: Economy Mode (334× A, 279× B). Đắt nhất nhưng vẫn rẻ: VIP Concierge (10.8× A, 8.5× B).

Tuy nhiên cần lưu ý khi so sánh:
- Human $0.50/conv đã bao gồm booking và complaint handling — nhân viên làm tất cả
- AI $0/conv cho booking và complaint chỉ là handoff, vẫn cần nhân viên sales xử lý
- AI chatbot thay thế được ~85% (Scenario A) / 55% (Scenario B) workload information query
- Vẫn cần ít nhất 1 nhân viên sales + 1 manager → fixed human cost $1,500–$3,000/tháng
- Tổng cost thực tế = AI monthly + fixed human → vẫn thấp hơn thuê đội support 5+ người

Nếu sếp hỏi "justify VIP Concierge đắt hơn 4.9× Smart Balance?":
→ 24/7 availability + 10+ ngôn ngữ + không mệt mỏi sau peak season
→ Nếu khách VIP book tour trung bình $4,000 và VIP Concierge giúp convert thêm 1 khách/tháng
   → additional revenue $4,000 >> extra cost $1,397 (2,115 − 718) → justify được
→ Nhưng cần đo conversion rate thực tế để confirm
```

---

## Bảng kiểm trước khi sang file tiếp theo

- [x] Bảng đầy đủ — không còn ô trống
- [x] Đã có 4 câu trả lời cho 4 quan sát ở trên
- [x] Nhóm đồng thuận về số trong bảng (đã sanity check)

Xong → mở `05-recommendation.md` để viết recommendation cuối + chuẩn bị present.
