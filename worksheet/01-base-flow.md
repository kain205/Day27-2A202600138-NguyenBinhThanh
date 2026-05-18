# 01 · Base Flow + Chốt 3 Knobs

> **Mục tiêu**: Hiểu chatbot hoạt động ra sao ở mức base (không chọn config gì) — và xác định 3 knobs nhóm sẽ tweak ở các bước sau.
>
> **Thời gian**: 7 phút (trong 15 phút phần Setup)

---

## Bước 1 — Đọc base flow trong cost reference card

Mở file `cost-reference-card.md` ở phần **2. Base Flow** — xem flow chatbot mặc định. Đây là cấu trúc mọi config sẽ build dựa trên.

Đọc xong, tự kiểm tra hiểu:

- Khi tourist gửi tin nhắn, AI làm gì đầu tiên?
- 5 intent dẫn đến 5 hành động khác nhau — hành động nào tốn LLM, hành động nào không?
- Sau khi route, AI ráp gì lại để generate response?

Nếu chưa hiểu → quay lại đọc lại 1 lần nữa. Đừng đi tiếp khi còn mơ hồ.

---

## Bước 2 — Vẽ lại flow theo cách hiểu của nhóm

```text
Tourist gửi tin nhắn (tiếng Anh)
            │
            ▼
┌─ INTENT CLASSIFIER ──────────────────────────────────────────┐
│  Keyword matching phân loại ý định của khách                   │
│  → Visa/Policy | Guide/Destination | Weather/Event           │
│  → Tour/Booking | Complaint                                  │
└────┬──────────────┬──────────┬──────────┬───────────────────┘
     │              │          │          │            │
     ▼              ▼          ▼          ▼            ▼
  Visa/Policy   Guide/Dest  Weather   Booking      Complaint
     │              │          │          │            │
     ▼              ▼          ▼          ▼            ▼
  RAG lookup    RAG lookup  Web search  Handoff     Escalate
  + Web search? (KB đủ)    (real-time)  Sales ($0)  Manager ($0)
     │              │          │
     └──────────────┴──────────┘
                    │
                    ▼
┌─ CONTEXT ASSEMBLY ───────────────────────────────────────────┐
│  System prompt (500 tokens)                                   │
│  + Chat history (Last 3 / Last 5 / Full — tùy config)        │
│  + RAG top-5 chunks (1,250 tokens)                           │
│  + Web search results (800 tokens — nếu bật)                 │
│  + User message (80 tokens)                                  │
└────────────────────────┬─────────────────────────────────────┘
                         │
                         ▼
┌─ RESPONSE GENERATION ────────────────────────────────────────┐
│  Model tạo câu trả lời tiếng Anh cho khách                    │
│  (180 tokens output trung bình)                              │
└──────────────────────────────────────────────────────────────┘
```

**Lưu ý quan trọng khi vẽ:**
- Booking + Complaint → handoff ngay → **$0 LLM cost** (chỉ tốn classifier)
- Visa cần web search vì policy thay đổi thường xuyên theo quốc gia (UK, Đức, Hàn...)
- Weather luôn cần web search vì đây là thông tin real-time (mưa, bão, lũ miền Trung)
- Guide dùng RAG là đủ — knowledge base static đã cover điểm đến, ẩm thực, vận chuyển tốt
- History được cộng vào mỗi turn → chi phí tăng dần theo độ dài conversation

---

## Bước 3 — Xác định 3 Knobs

3 knobs là 3 quyết định thiết kế có thể tweak. Mỗi config = 1 bộ chọn tại 3 knobs này.

### Knob 1 — Model tier

**Câu hỏi:** Chất lượng câu trả lời ở mức nào?

Options:

```text
□ Cheap        (Gemini Flash-Lite / DeepSeek V4 Flash / GPT-4o-mini)
□ Mid          (Gemini Flash / Claude Haiku 4.5)
□ Strong       (DeepSeek V4 Pro / Claude Sonnet 4.6)
□ Premium      (Claude Opus 4.7 / GPT-5.5)
☑ Mix          (model khác nhau cho intent khác nhau — viết rõ bên dưới)
```

```text
Suy nghĩ:
- Câu hỏi Guide (food, transport, itinerary): knowledge base đã cover tốt
  → model rẻ GPT-4o-mini là đủ để format và present thông tin
- Câu hỏi Visa: phức tạp hơn — policy theo từng quốc tịch (UK, Đức, Hàn),
  cần xử lý chính xác web context dài → nên dùng model trung bình (Haiku 4.5)
- Chênh lệch: GPT-4o-mini ($0.15/$0.60) vs Claude Sonnet ($3/$15) → đắt hơn 20×
- Chiến lược: dùng đúng "trí thông minh" cho đúng loại câu hỏi
```

### Knob 2 — Web search

**Câu hỏi:** Có cần thông tin real-time không?

Options:

```text
□ OFF              (chỉ dùng RAG — knowledge base có sẵn)
☑ ON selective    (bật cho 1–2 intent cần real-time: visa, weather)
□ ON broad         (bật cho hầu hết intent)
```

```text
Suy nghĩ:
- Visa policy UK, Đức, Hàn thay đổi theo thời gian (VN mở e-visa, kéo dài thời hạn...)
  → chatbot trả lời outdated = khách bị từ chối nhập cảnh → bad review nghiêm trọng
- Weather: real-time tự nhiên — đặc biệt quan trọng cho khách hỏi mùa bão miền Trung
- Guide: knowledge base static đủ tốt — "top food in Hoi An" không cần real-time
- ON broad: lãng phí $0.008/query + 800 tokens mỗi turn không cần thiết
- Kết luận: ON selective (Visa + Weather) là điểm cân bằng đúng
```

### Knob 3 — History management

**Câu hỏi:** Chatbot cần nhớ bao nhiêu context của conversation?

Options:

```text
□ Last 3 turns        (nhẹ nhất, dễ quên)
□ Last 5 turns        (cân bằng)
□ Full history        (nhớ tất cả, đắt nhất ở conv dài)
□ Summarize every 5   (nâng cao — cần 1 LLM call phụ để tóm tắt)
```

```text
Suy nghĩ:
- Emma (tourist Đức) hỏi vaccination turn 1, turn 4 hỏi hospital cho trẻ → nếu Last 3
  sẽ không nhớ "gia đình có trẻ 7 tuổi" → trả lời generic thay vì pediatric care
- Last 5: đủ cho Scenario A (4 turns), Scenario B mất 2 turns đầu (thường là greeting)
  → chấp nhận được vì greeting không chứa info quan trọng
- Full: Scenario B turn 7 thêm 1,560 tokens history → với Sonnet đắt thêm ~$0.005/turn
- Kết luận: Last 3 cho Economy, Last 5 cho Smart Balance, Full cho VIP Concierge
```

---

## Bước 4 — Sơ bộ các combo sẽ thử

**Combo 1 (định hướng cheap)**:

```text
Model: GPT-4o-mini (tất cả intents)    Web: OFF    History: Last 3
Đặt tên dự kiến: "Economy Mode"
```

**Combo 2 (định hướng premium)**:

```text
Model: Claude Sonnet 4.6 (tất cả intents)    Web: ON selective (Visa+Weather)    History: Full
Đặt tên dự kiến: "VIP Concierge"
```

**Combo 3 (định hướng balanced)**:

```text
Model: GPT-4o-mini cho Guide/Weather, Claude Haiku 4.5 cho Visa    Web: ON selective    History: Last 5
Đặt tên dự kiến: "Smart Balance"
```

**Combo 4** (optional):

```text
Model: Gemini 2.5 Flash-Lite (tất cả intents)    Web: ON selective (Visa+Weather)    History: Last 5
Đặt tên dự kiến: "Google Lite" — thử provider khác với giá thấp nhất thị trường
```

---

## Bảng kiểm trước khi sang file tiếp theo

- [x] Đã vẽ flow base có đủ 4 bước (Intent → Route → Context → Response)
- [x] Hiểu Booking + Khiếu nại = $0 LLM cost (chuyển con người)
- [x] Đã phác thảo ≥3 combo khác nhau (chưa cần chi tiết)
- [x] Nhóm đồng thuận về hướng đi mỗi combo

Xong → 10:25 chuyển sang **Main phase**. Mở `02-config-design.md`.
