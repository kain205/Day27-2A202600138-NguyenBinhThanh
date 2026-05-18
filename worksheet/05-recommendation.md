# 05 · Recommendation + Justification — Kết luận & Chuẩn bị Present

> **Mục tiêu**: Chọn 1 config (hoặc combo) nhóm recommend deploy, viết justification ngắn gọn, và chuẩn bị 5 phút present.
>
> **Thời gian**: 10 phút (cuối phần Final) — Pens down lúc 12:00

---

## Bảng số ai cũng tính được. PM giỏi phải **recommend** và **justify**.

Đây là phần quan trọng nhất — phần phân biệt nhóm chỉ làm xong với nhóm thực sự hiểu sản phẩm.

---

## 4 câu hỏi nhóm phải trả lời

Mỗi câu trả lời 2–4 câu. Không lan man, không clichés. Mỗi câu phải justify được bằng số trong bảng so sánh.

### Câu 1 — Recommend config nào?

Trước khi viết, thảo luận 1 phút:

- Recommend 1 config duy nhất chạy quanh năm? Hay 2 configs khác nhau cho mùa thấp / mùa cao?
- Có nên recommend "Smart Mix model theo intent" thay vì pick 1 config cố định không?
- Nếu sếp nói "chỉ deploy 1 config thôi" — chọn cái nào?

```text
Nhóm recommend Smart Balance (Config 3) làm config chính chạy quanh năm, với option
nâng model Visa từ Haiku 4.5 lên Sonnet 4.6 trong mùa cao điểm nếu accuracy dưới 90%.

Lý do không chọn Economy Mode: web search hoàn toàn tắt → visa info của UK, Đức, Hàn Quốc
có thể outdated → 1 lần chatbot trả lời sai về e-visa requirements → Emma (Đức) bị từ chối
nhập cảnh → bad review công khai → thiệt hại mất khách vượt xa khoản tiết kiệm $132/tháng
so với Smart Balance ($146.04 - $13.49 = $132.55/tháng Scenario A).

Lý do không chọn VIP Concierge làm config duy nhất: đắt gấp 2.9× Smart Balance ở Scenario B
($2,115 vs $718) nhưng chỉ tăng 1 bậc quality (Med-High → High) — không justify về mặt kinh
tế trừ khi đo được conversion rate tăng cụ thể. Nếu sếp bắt buộc chọn 1 config duy nhất: Smart Balance.
```

### Câu 2 — So với human baseline $0.50/conv → tiết kiệm bao nhiêu? Có đắt hơn human ở chỗ nào không?

```text
Smart Balance tiết kiệm 96.8% ở Scenario A (tiết kiệm $4,353.96/tháng so với human $4,500)
và 96.0% ở Scenario B (tiết kiệm $17,282.10/tháng so với human $18,000).
Tổng tiết kiệm ước tính cả năm: $130,000–$200,000 so với model pure human support.

AI không đắt hơn human ở bất kỳ config nào trong bảng so sánh. Tuy nhiên cần lưu ý:
AI chatbot chỉ thay thế được phần "information query" — vẫn cần ít nhất 1 nhân viên sales
để xử lý booking conversion và 1 manager cho escalation. Cost thực tế = AI monthly ($718
Scenario B) + fixed human ($1,500–$2,000/tháng cho 1–2 người) ≈ $2,218–$2,718/tháng.
Vẫn thấp hơn đáng kể so với đội support đầy đủ 5–8 người ($7,500–$12,000/tháng).

Lợi thế AI ngoài tiết kiệm: hoạt động 24/7, phục vụ đồng thời nhiều khách quốc tế,
nhất quán về accuracy và tone, không cần onboarding khi có nhân viên mới.
```

### Câu 3 — Khi nào nên upgrade / downgrade config?

Trước khi viết, tự hỏi:

- Volume bao nhiêu thì cost AI scale lớn hơn benefit?
- Quality complaint rate bao nhiêu thì biết Economy Mode không đủ?
- Có signal nào báo nên chuyển sang Premium? (mùa cao điểm bắt đầu? customer feedback?)

```text
Nên UPGRADE từ Smart Balance → nâng model Visa lên Sonnet 4.6 khi:
- Bắt đầu peak season (tháng 7–8, tháng 12–1) khi volume vượt 800 conv/ngày
- Customer feedback report visa answer accuracy dưới 90%
- VN thay đổi chính sách visa lớn (mở thêm countries, đổi e-visa system)
  → context mới nhiều và phức tạp hơn → Haiku có thể xử lý kém hơn

Nên DOWNGRADE về Economy Mode cho specific use cases:
- Night shift (00:00–06:00): volume thấp, khách hỏi đơn giản → GPT-4o-mini toàn bộ + web OFF
  → tiết kiệm thêm mà rủi ro visa thấp hơn (ít người hỏi visa lúc nửa đêm)
- Nếu budget tháng bị cắt khẩn cấp và target < $50/tháng → fallback Economy Mode
  với cảnh báo nội bộ về visa risk

Monitor để quyết định: cost/tháng (alert nếu vượt $1,500 đột biến), visa complaint rate
(target < 2%), avg conversation rating (target ≥ 4.0/5).
```

### Câu 4 — Rủi ro lớn nhất của config được chọn?

Trước khi viết, tự hỏi:

- Rủi ro về quality? (visa info outdated? language mismatch?)
- Rủi ro về cost? (provider tăng giá? volume spike?)
- Rủi ro về business? (khách bị bot trả lời sai → bad review → mất khách?)
- Có mitigation plan không?

```text
Rủi ro #1 — Routing error (classify sai Visa → Guide):
Keyword classifier có thể nhận nhầm "how do I get into Vietnam without a tourist visa"
là Guide thay vì Visa → dùng GPT-4o-mini → accuracy thấp hơn cho câu hỏi visa policy.
Mitigation: test classifier với ≥50 câu hỏi visa edge cases; fallback rule: nếu message
chứa keywords "visa/passport/entry/e-visa/document/permit" → luôn route Visa intent.

Rủi ro #2 — Provider price increase:
Anthropic tăng giá Haiku 4.5 lên 30% → Smart Balance tăng ~$35/tháng ở Scenario B — acceptable.
Nếu tăng 2×: monthly B = ~$1,436 → vẫn ok. Nếu tăng 5×: ~$3,590 → cần review lại.
Mitigation: monitor giá hàng quý, sẵn sàng swap Haiku 4.5 sang DeepSeek V4 Flash
(quality tương đương, ~3× rẻ hơn) nếu Anthropic tăng giá >50%.

Rủi ro #3 — Web search latency / downtime:
Tavily có downtime hoặc slow response → Weather/Visa turns chậm 5–10s → bad UX.
Mitigation: timeout 3s cho web search → fallback về RAG nếu timeout, kèm disclaimer
"Information may not reflect latest updates. Please verify with official sources."
```

---

## Final answer — Recommendation in 1 paragraph

Tổng hợp 4 câu trên thành 1 paragraph 5–7 câu — đây là phần nhóm sẽ đọc / chiếu khi present.

```text
Nhóm recommend triển khai Smart Balance (Config 3) làm cấu hình chính cho chatbot travel
agency: GPT-4o-mini cho Guide/Weather, Claude Haiku 4.5 cho Visa, web search bật cho Visa
và Weather, lịch sử Last 5 turns. Config này tiết kiệm 96.8% so với human support ($146/tháng
vs $4,500 mùa thấp điểm; $718/tháng vs $18,000 mùa cao điểm) trong khi đảm bảo visa
information chính xác — rủi ro quan trọng nhất cần tránh cho travel agency phục vụ khách quốc tế.
Economy Mode rẻ hơn 10.8× nhưng web OFF tạo rủi ro nghiêm trọng: 1 lần trả lời sai visa
(UK e-visa, German family visa) có thể gây bad review và mất khách, thiệt hại vượt xa khoản
tiết kiệm $132/tháng. VIP Concierge đắt gấp 2.9× Smart Balance nhưng chỉ tăng 1 bậc quality —
không justify trừ khi conversion rate tăng đo được ≥1 khách VIP ($4,000/booking) mỗi tháng.
Trong mùa cao điểm, có thể nâng model Visa từ Haiku lên Sonnet nếu accuracy feedback dưới 90%.
Rủi ro chính cần monitor: intent routing accuracy cho Visa và API price changes theo quý.
```

---

## Chuẩn bị Present (5 phút)

### Nhịp 0:00 – 0:30 — Base flow + 3 knobs đã chọn

Ai trình bày: **Thành**

Nói gì:

```text
"Chatbot travel agency xử lý 5 intents: Visa, Guide, Weather, Booking, Complaint.
Booking và Complaint handoff ngay sang nhân viên — $0 LLM cost. Nhóm tweak 3 knobs:
model tier, web search, và history length. 3 knobs này quyết định 90% cost và quality."
```

### Nhịp 0:30 – 1:00 — Config overview

Ai trình bày: **Thành**

Nói gì (đọc nhanh tên + knobs 3 configs):

```text
"Config 1 — Economy Mode: GPT-4o-mini, web OFF, Last 3 turns. Rẻ nhất nhưng rủi ro visa.
Config 2 — VIP Concierge: Sonnet 4.6, web ON Visa+Weather, Full history. Mạnh nhất, đắt nhất.
Config 3 — Smart Balance: Haiku cho Visa, GPT-4o-mini cho phần còn lại, web ON selective, Last 5."
```

### Nhịp 1:00 – 2:00 — Cost comparison

Ai trình bày: **Thành**

Nói gì (chiếu bảng so sánh, highlight rẻ nhất / đắt nhất):

```text
"Economy Mode monthly B = $65, VIP Concierge = $2,115, Smart Balance = $718.
Tất cả đều rẻ hơn human baseline $18,000 từ 8.5× đến 279×.
Chênh giữa rẻ nhất và đắt nhất là 32.7× — nhưng quality gap chỉ Low-Med vs High.
VIP đắt hơn Smart Balance 2.9× nhưng quality chỉ tăng 1 bậc → diminishing returns rõ."
```

### Nhịp 2:00 – 3:00 — Key insight

Ai trình bày: **Thành**

Nói gì (knob nào ảnh hưởng cost nhiều nhất + tại sao):

```text
"Model tier là knob ảnh hưởng cost lớn nhất: GPT-4o-mini vs Sonnet chênh 20× về input price.
Insight bất ngờ: Scenario B không đắt ×7 mà chỉ ×4.8 vì Booking 35% + Complaint 10% = $0 LLM
— mùa cao điểm có nhiều booking hơn nhưng booking = handoff = free → tự cân bằng cost."
```

### Nhịp 3:00 – 4:30 — Recommendation + justification

Ai trình bày: **Thành**

Nói gì (đọc paragraph "Final answer" ở trên):

```text
"Nhóm recommend Smart Balance — $146/tháng mùa thấp, $718/tháng mùa cao, tiết kiệm 96%.
Economy Mode rẻ hơn 10× nhưng visa info outdated = rủi ro mất khách > tiết kiệm $132/tháng.
VIP Concierge đắt gấp 2.9× — không justify trừ khi đo được conversion rate tăng.
Smart Balance là điểm ngọt: đủ chính xác cho visa, đủ rẻ để scale, đủ linh hoạt để upgrade."
```

### Nhịp 4:30 – 5:00 — Hardest question prep

Ai trình bày: **Thành**

Nhóm dự đoán câu hỏi khó nhất sẽ bị hỏi là gì?

```text
"Nếu Haiku 4.5 trả lời visa sai và khách Đức bị từ chối nhập cảnh — nhóm chịu trách
nhiệm thế nào? Tại sao không dùng Sonnet cho visa để an toàn hơn?"
```

Câu trả lời sẵn:

```text
"Đây là rủi ro thật và nhóm đã tính đến. Haiku 4.5 với web search ON bật mỗi turn sẽ fetch
thông tin visa fresh — đây là mitigation chính cho outdated risk. Thêm vào đó, chatbot nên
hiển thị disclaimer trên mọi câu trả lời visa: 'Please verify with the official Vietnam
Immigration portal or contact our staff for official confirmation.'
Nếu complaint rate về visa accuracy vượt 2%, trigger upgrade Visa model lên Sonnet ngay —
extra cost ~$200/tháng, nhỏ hơn nhiều so với 1 bad review viral."
```

---

## Q&A — 2 phút sau khi present xong

**3 câu instructor thường hỏi**:

1. *"Knob nào ảnh hưởng cost nhiều nhất trong config của nhóm? Tại sao?"*
2. *"Nếu provider tăng giá API ×2 → config của nhóm còn sống được không?"*
3. *"So với nhóm X (vừa present trước) — tại sao nhóm bạn chọn khác?"*

Suy nghĩ trước câu trả lời ngắn:

```text
1. Model tier — GPT-4o-mini vs Sonnet chênh 20× về input price, chiếm phần lớn monthly cost.
   Web search là knob #2 nhưng quan trọng hơn với model rẻ (web cost = ~94% of turn cost
   khi dùng GPT-4o-mini), còn với Sonnet thì model cost là chủ đạo.

2. Smart Balance nhân đôi API price: Haiku lên $2/$10, GPT-4o-mini lên $0.30/$1.20 →
   Smart Balance monthly B tăng từ $718 lên ~$1,436. Vẫn rẻ hơn human $18,000 khoảng 12.5×.
   Sống được. Nếu tăng ×5 (~$3,590) → cần review, swap Haiku sang DeepSeek V4 Flash.

3. Smart Balance chọn routing theo intent để dùng đúng model cho đúng loại câu hỏi — 
   đây là điểm khác biệt cốt lõi so với config chọn 1 model cho tất cả.
```

---

## Bảng kiểm cuối cùng — trước 12:00 Pens Down

- [x] Đã trả lời 4 câu PM (Recommend / Savings / Threshold / Risk)
- [x] Final answer paragraph viết gọn (5–7 câu)
- [x] Phân công 5 nhịp present cho mỗi thành viên
- [x] Có sẵn câu trả lời cho 3 câu Q&A dự đoán
- [x] Comparison table có sẵn để chiếu / chuyền tay khi present
- [ ] Repo đã commit + push (sẽ nộp link sau buổi học)

---

## Sau buổi học

1. **Commit + push repo** với tất cả file đã điền.
2. **Dán link repo** vào Discord `#day27-evidence-boards` trước 23:59.
3. **Chuẩn bị cho D28**: peer review giữa các nhóm — sẽ bị hỏi câu chất vấn khó hơn instructor. Polish thêm bảng + recommendation tối nay.

*Hôm nay bạn chứng minh bằng số. Ngày mai bạn bảo vệ bằng logic.*
