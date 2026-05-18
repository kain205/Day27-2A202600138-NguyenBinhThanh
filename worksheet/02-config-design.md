# 02 · Configuration Design — Đặt tên + Chốt knobs cho ≥3 Configs

> **Mục tiêu**: Biến phác thảo ở `01-base-flow.md` thành ≥3 configurations chi tiết, mỗi config có tên + 3 knobs đã chốt + lý do chọn.
>
> **Thời gian**: 15 phút (đầu phần Main, trước khi tính cost)

---

## Tại sao đặt tên + viết lý do?

Khi present, nhóm sẽ nói "Config 1, Config 2, Config 3" → người nghe sẽ chán ngay. Đặt tên gợi mở (Economy Mode, VIP Concierge, Smart Balance...) giúp memorable + cho thấy nhóm hiểu rõ tradeoff. Viết lý do giúp nhóm tự kiểm tra: "Mình chọn config này vì lý do gì? Có justify được không?"

---

## Cách điền

Với mỗi config: đặt tên + chốt 3 knobs + viết 2–3 câu lý do chọn. Mỗi câu lý do phải gắn với 1 tình huống thực tế (volume thấp / khách hỏi visa nhiều / budget bị siết...).

Tham khảo bảng pricing chi tiết tại `cost-reference-card.md` mục **3. Decision Points**.

---

## Config 1

**Tên config**: "Economy Mode"

```text
Economy Mode
```

### 3 Knobs

**① Model tier**:

```text
Response model: GPT-4o-mini → giá $0.15 / $0.60 per 1M tokens (input/output)
Classifier model: keyword/regex → $0 (không dùng LLM cho classification)
```

**② Web search**:

```text
☑ OFF
□ ON selective — bật cho intent: __________________
□ ON broad
```

**③ History management**:

```text
☑ Last 3
□ Last 5
□ Full
□ Summarize every ___ turns
```

### Lý do nhóm chọn config này

Trước khi viết, tự hỏi:

- Config này phục vụ tình huống nào tốt nhất? (mùa thấp điểm? night-time? volume cao đột biến?)
- Trade-off chính là gì? (Rẻ nhưng kém chất lượng? Đắt nhưng chính xác?)
- Khách hàng nào sẽ hài lòng nhất với config này? Khách nào sẽ thất vọng?

```text
Economy Mode phù hợp nhất cho mùa thấp điểm (300 conv/ngày) khi cần kiểm soát chi phí
tối đa và phần lớn câu hỏi là Guide FAQ đơn giản — knowledge base tĩnh là đủ cho tourist
hỏi "top food in Hoi An" hay "how to get from Hanoi to Ha Long Bay".
Khách hỏi itinerary hoặc food recommendation sẽ hài lòng vì GPT-4o-mini nhanh và đủ tốt
với RAG context. Tuy nhiên khách hỏi visa chi tiết (UK e-visa, German family visa) hoặc
cần nhớ ngữ cảnh từ đầu conversation sẽ thấy câu trả lời kém chính xác hơn.
```

### Rủi ro lớn nhất của config này

```text
Web search OFF → visa info có thể outdated khi VN thay đổi policy (ví dụ: kéo dài thời hạn
e-visa từ 90 lên 180 ngày) → chatbot trả lời sai → khách như Emma (Đức) bị từ chối nhập
cảnh hoặc không chuẩn bị đúng giấy tờ → bad review nghiêm trọng nhất cho travel agency.
```

---

## Config 2

**Tên config**: "VIP Concierge"

```text
VIP Concierge
```

### 3 Knobs

**① Model tier**:

```text
Response model: Claude Sonnet 4.6 → giá $3.00 / $15.00 per 1M tokens (input/output)
Classifier model: keyword/regex → $0
```

**② Web search**:

```text
□ OFF
☑ ON selective — bật cho intent: Visa/Policy và Weather/Event (mỗi turn của 2 intent này)
□ ON broad
```

**③ History management**:

```text
□ Last 3
□ Last 5
☑ Full
□ Summarize every ___ turns
```

### Lý do nhóm chọn config này

```text
VIP Concierge là config cao cấp cho khách muốn tư vấn tour dài ngày và đặt tour đắt tiền
($3,000–$5,000/người) — 1 câu trả lời sai về visa hoặc thời tiết có thể mất booking giá trị cao.
Claude Sonnet 4.6 xử lý tốt câu hỏi phức tạp như "lộ trình 10 ngày cho gia đình có trẻ nhỏ
từ Ha Long → Hoi An → Phu Quoc" hoặc so sánh tour packages. Web ON selective đảm bảo visa
và weather luôn fresh (tourist như James hỏi UK e-visa cần thông tin chính xác nhất).
Full history đảm bảo chatbot nhớ "gia đình 3 người, trẻ 7 tuổi, budget $5,000" từ turn 1 đến turn 7.
```

### Rủi ro lớn nhất của config này

```text
Cost tăng phi tuyến khi conversation dài: Turn 7 Scenario B với Full history và Sonnet
tốn ~4,190 input tokens/turn → monthly Scenario B có thể vượt $1,900 — đắt gấp ~30× Economy Mode.
Cần justify rõ bằng conversion rate từ khách VIP để sếp chấp nhận chi phí cao.
```

---

## Config 3

**Tên config**: "Smart Balance"

```text
Smart Balance
```

### 3 Knobs

**① Model tier**:

```text
Response model (Guide + Weather): GPT-4o-mini → giá $0.15 / $0.60 per 1M tokens
Response model (Visa/Policy): Claude Haiku 4.5 → giá $1.00 / $5.00 per 1M tokens
(Lý do split: Visa cần accuracy cao + web context dài; Guide/Weather thì RAG/web search
đã làm phần nặng — model chỉ cần format và present kết quả)
Classifier model: keyword/regex → $0
```

**② Web search**:

```text
□ OFF
☑ ON selective — bật cho intent: Visa/Policy và Weather/Event
□ ON broad
```

**③ History management**:

```text
□ Last 3
☑ Last 5
□ Full
□ Summarize every ___ turns
```

### Lý do nhóm chọn config này

```text
Smart Balance áp dụng nguyên tắc "dùng đúng công cụ cho đúng công việc": Visa cần Haiku 4.5
để xử lý chính xác thông tin nhạy cảm có web context, còn Guide/Weather chỉ cần GPT-4o-mini
để format output từ RAG/web. Last 5 là điểm ngọt: Scenario A (4 turns) giữ full context,
Scenario B (7 turns) chỉ mất 2 turns đầu (greeting/clarification) — không ảnh hưởng thực chất.
Web ON selective cho Visa + Weather đảm bảo 2 intent rủi ro nhất luôn có thông tin fresh.
```

### Rủi ro lớn nhất của config này

```text
Routing logic phức tạp hơn: nếu classifier nhận nhầm câu hỏi "how to enter Vietnam safely"
là Guide thay vì Visa → dùng GPT-4o-mini → câu trả lời visa không đủ chính xác.
Cần test classifier kỹ với ≥50 câu hỏi edge cases visa trước khi deploy.
```

---

## Config 4 (optional — nếu thời gian dư)

Nhóm có thể thiết kế thêm config thứ 4 để có thêm điểm so sánh. Không bắt buộc.

**Tên config**:

```text
Google Lite (Gemini variant)
```

### 3 Knobs

```text
Model: Gemini 2.5 Flash-Lite ($0.10/$0.40) — rẻ nhất trong tất cả providers    
Web: ON selective (Visa + Weather)
History: Last 5
```

### Lý do

```text
Thử Google provider với giá thấp nhất ($0.10 input) + web search ON selective để so sánh
với Economy Mode (GPT-4o-mini, web OFF). Nếu Google Lite rẻ hơn Economy Mode nhưng vẫn
có web search cho visa/weather → đây là config tốt hơn Economy Mode về risk/cost ratio.
Mục đích: kiểm tra xem provider nào cho cost/quality ratio tốt nhất ở cheap tier.
```

---

## Bảng kiểm trước khi tính cost

- [x] ≥3 configs đã đặt tên (không chỉ "Config 1/2/3")
- [x] Mỗi config đã chốt rõ 3 knobs (không còn ô trống)
- [x] Mỗi config có ≥2 câu lý do
- [x] 3 configs đủ khác biệt — Economy (cheap/no web/short hist) vs VIP Concierge (strong/web/full hist) vs Smart Balance (mixed model/web/mid hist)
- [x] Nhóm đồng thuận đây là 3 configs đáng so sánh

**Nếu 3 configs quá giống nhau** (chỉ đổi model, knobs khác giống hệt) → quay lại tweak. Mục đích là thấy tradeoff — configs giống nhau quá → không thấy tradeoff.

Xong → mở `03-cost-calculation.md` để bắt đầu tính cost.
