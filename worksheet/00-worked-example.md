---
title: 00 — Ví dụ mẫu đã làm sẵn (Đề bài #1 — AI Support Copilot)
phan: Tham chiếu cho cả 3 bước Lab
format: Đọc trước Lab — không phải file để điền
thoi-gian: 10 phút đọc
---

# 00 — Ví dụ mẫu: AI Support Copilot (Đề bài #1)

File này là **một bản Economics Sheet đã điền hoàn chỉnh** cho Đề bài #1 (AI Support Copilot). Đây là mức chi tiết và độ chính xác mà nhóm cần đạt khi nộp bản cuối của mình.

## Cách dùng file này

- Đọc trước Lab để hình dung **bản nộp cuối trông như thế nào**.
- Khi nhóm bí ở một phần cụ thể, mở file này xem cách trình bày tham chiếu.
- **Không sao chép số sang đề bài khác** — mỗi đề bài có ngữ cảnh riêng. Sao chép = trừ 15 điểm (xem rubric).

Số trong file khớp với slide 13-14 và câu lệnh trong `prompts/05-value-formula.md`. Đề bài #1 được chọn làm ví dụ vì có ràng buộc 100% người kiểm tra trước khi gửi — đại diện cho dạng phổ biến nhất (chi phí kiểm tra chi phối toàn bộ chi phí).

---

## Thông tin nhóm (mẫu)

- **Đề bài**: #1 — AI Support Copilot
- **Cặp**: A20-99001 Nguyễn Mẫu A + A20-99002 Trần Mẫu B
- **Ngày tính**: 2026-05-14
- **Phiên bản**: v1 (ví dụ mẫu)

---

## Tóm tắt 1 câu cho người mua

> "CONDITIONAL GO cho Đề bài #1 — AI Support Copilot. ROI nền 2.07:1, kịch bản xấu kết hợp (tỷ lệ sử dụng thấp + nhà cung cấp tăng giá) còn 1.20:1 — biên rất mỏng. Pilot tiếp tục với 3 điều kiện cứng: tỷ lệ sử dụng ≥ 50% trước cuối tháng 1, khoá giá API 6 tháng, cổng chi phí $3,000/tháng."

---

## Section A — Cost Model (mô hình chi phí)

### A.1 — Đơn vị AI làm việc

| Trường | Giá trị |
|---|---|
| Tên ngắn | "1 bản nháp trả lời ticket" |
| Mô tả | AI nhận tiêu đề + nội dung ticket + 3 bài KB liên quan + lịch sử khách hàng, sinh ra 1 bản nháp 80–200 từ hiển thị trong panel bên Zendesk để agent sửa và gửi. |
| 3 câu kiểm tra | [x] Đếm được  [x] Tốn token  [x] Có giá trị cho người dùng |

### A.2 — Khối lượng

| Trường | Giá trị | Công thức / Nguồn |
|---|---|---|
| Người dùng trong nhóm thử nghiệm | 5 agent | Đề bài trường #8 |
| Tổng đội | 25 agent | Đề bài trường #1 |
| Khối lượng mỗi ngày của toàn đội | 800 ticket/ngày | Đề bài trường #1 |
| Khối lượng mỗi ngày của nhóm thử nghiệm | 160 ticket/ngày | (5/25) × 800 |
| Khối lượng mỗi tháng | 3,520 ticket/tháng | 160 × 22 ngày làm việc |

### A.3 — Mô hình + Chi phí API

| Trường | Giá trị | Nguồn |
|---|---|---|
| Nhà cung cấp chính | Anthropic | <https://www.anthropic.com/pricing> |
| Mô hình chọn | Claude 3.5 Sonnet | Trang giá Anthropic |
| Giá đầu vào ($/1M token) | $3.00 | Trang giá |
| Giá đầu ra ($/1M token) | $15.00 | Trang giá |
| Token đầu vào / một lần chạy | 6,000 | Ticket 500 từ + 3 bài KB (~1,500 từ mỗi bài) + system prompt + lịch sử khách |
| Token đầu ra / một lần chạy | 400 | Bản nháp 300 từ + header |
| Chi phí API / một lần chạy | $0.024 | (6,000 × $3 + 400 × $15) / 1,000,000 = $0.018 + $0.006 |

> **Ghi chú**: trên slide 13 dùng $0.05 cho gọn — đã cộng thêm chi phí tooling phân bổ theo việc và một biên dự phòng nhỏ. Ví dụ mẫu này dùng $0.05 để khớp slide.

| Chi phí mỗi lần chạy (làm tròn cho slide) | $0.05 | API + tooling phân bổ + biên dự phòng |

### A.4 — Chi phí công cụ phụ trợ

| Trường | Giá trị | Nguồn / Lý do |
|---|---|---|
| Vector DB | $70/tháng | Pinecone Starter (50K vectors, đủ cho 50K bài KB) |
| Giám sát | $50/tháng | Langfuse Pro tier (10K log/ngày) |
| Điều phối workflow | $30/tháng | n8n self-hosted + giấy phép |
| Tích hợp khác | $50/tháng | Zendesk app license |
| **Tổng / tháng** | **$200** | Cộng dồn |

### A.5 — Chi phí người kiểm tra

| Trường | Giá trị | Công thức / Lý do |
|---|---|---|
| Lương theo giờ của người kiểm | $25/giờ | Đề bài: agent senior $20/giờ × 1.25 (đã cộng phụ cấp) |
| Thời gian kiểm / một việc | 3 phút | Ràng buộc đề bài: 100% người kiểm trước khi gửi |
| Chi phí kiểm / một việc | $1.25 | (3/60) × $25 |
| Chi phí kiểm / tháng (gộp) | $4,400/tháng | 3,520 × $1.25 |

**Hiệu chỉnh cho ví dụ mẫu**: slide 13 dùng $2,427/tháng. Lý do: chỉ ~55% bản nháp thật sự được agent dùng (tỷ lệ sử dụng 65% × chất lượng 80% ≈ 52%, làm tròn lên 55%). Phần còn lại agent bỏ qua và viết tay — không tính chi phí kiểm cho phần đó.

| Chi phí kiểm hiệu dụng / một việc | $0.69 | $1.25 × 55% |
| Chi phí kiểm hiệu dụng / tháng | $2,427/tháng | 3,520 × $0.69 |

### A.6 — Chi phí setup (phân bổ)

| Trường | Giá trị | Lý do |
|---|---|---|
| Setup một lần | $0 (đã xong) | Tích hợp + tinh chỉnh prompt đã làm trong tháng 0 trước pilot, không tính vào ngân sách tháng pilot |
| Thời gian pilot | 3 tháng | Đề bài trường #8: 90 ngày |
| Setup phân bổ / tháng | $0 | Đã ghi vào tháng 0 |

> **Ghi chú thực tế**: setup ($4,000-$8,000) thường phân bổ ra $1,300-$2,700/tháng. Ví dụ mẫu bỏ qua để khớp slide. **Nhóm khác bắt buộc phải tính phần phân bổ này.**

### A.7 — Công thức chi phí mỗi tháng

```text
Chi phí AI mỗi tháng
  = (3,520 × $0.05)        = $176        [API + tooling theo việc]
  + $200                    = $200        [Tooling cố định]
  + (3,520 × $0.69)        = $2,427      [Người kiểm hiệu dụng]
  + $0                      = $0          [Setup đã ghi tháng 0]
                            ──────────
                            = $2,803 /tháng TỔNG
```

### A.8 — Đối chiếu ngân sách

| Trường | Giá trị |
|---|---|
| Tổng chi phí tháng | $2,803 |
| Ngân sách pilot | $5,000 (đề bài trường #8) |
| % ngân sách dùng | 56% |
| Trạng thái | [x] Trong ngân sách  [ ] Vượt ngân sách |

### Section A — 3 nhận xét chính

1. **Chi phí lớn nhất là người kiểm**: $2,427 / $2,803 = 87% tổng chi phí. API chỉ chiếm 6%. Đây là dạng phổ biến khi đề bài có ràng buộc 100% người kiểm.
2. **Chi phí bất ngờ**: tooling rẻ hơn dự đoán ($200 cho 4 công cụ). Setup nếu phân bổ đúng sẽ đẩy tổng lên $4,000+ — gần vượt ngân sách.
3. **Độ nhạy**: chi phí nhạy nhất với **thời gian kiểm mỗi việc**. Cứ thêm 1 phút kiểm là $1,173/tháng. Quan trọng hơn cả chọn mô hình rẻ.

---

## Section B — Mô hình định giá (Pricing / Access)

### B.1 — Vị trí trên ma trận Attribution × Autonomy

| Trường | Giá trị | Lý do |
|---|---|---|
| Mức tự chủ (Autonomy) | Thấp | Agent ra quyết định cuối, AI chỉ gợi ý. Ràng buộc 100% kiểm = autonomy thấp cứng. |
| Mức gán giá trị (Attribution) | Thấp đến Trung | Khó tách "AI viết" khỏi "agent sửa". Người mua không thấy rõ AI tạo giá trị độc lập. |
| Ô trên ma trận | Autonomy thấp + Attribution thấp/trung | → Seat-based hoặc Hybrid nghiêng về Seat |

### B.2 — Mô hình định giá

| Trường | Giá trị |
|---|---|
| Mô hình chọn | Hybrid (Seat + Credits) |
| Cấu trúc giá cụ thể | $25/seat/tháng + 1,000 credit/seat. Credit thêm $0.05. |
| Chỉ số tính giá (value metric) | "1 bản nháp trả lời được sinh" (đếm được, agent thấy cụ thể, gắn với việc AI làm) |
| Người mua (vai trò) | CTO / Director Support |
| Lý do mua bây giờ | Đề bài trường #3: 18% churn liên quan support, thuê thêm 5 agent = $300K/năm → AI tiết kiệm > $200K nếu đạt tỷ lệ sử dụng. |

### B.3 — Sản phẩm tương đương trên thị trường

| Trường | Giá trị |
|---|---|
| Sản phẩm tương đương | Cursor AI |
| Cách họ định giá | $20/seat + 500 fast credit, credit thêm $0.04/request |
| Vì sao tương đương | Autonomy thấp (dev kiểm code suggest), attribution trung (theo từng tính năng), pricing hybrid đã chứng minh khả thi với người mua kỹ thuật. |

### B.4 — Kiểm tra Usage Anxiety (nỗi sợ dùng nhiều bị tính phí cao)

| Trường | Giá trị |
|---|---|
| Mức rủi ro Usage Anxiety | Trung |
| Cách giảm thiểu | (1) Cap mềm ở 80% credit: chỉ cảnh báo nhẹ, không chặn. (2) Dashboard admin hiển thị tổng usage cả đội, không bill shock cá nhân. (3) Tháng đầu miễn phí 100 credit khám phá cho mỗi agent. |

---

## Section C — Giá trị / ROI

### C.1 — Thời gian tiết kiệm mỗi việc

| Trường | Giá trị | Lý do |
|---|---|---|
| Thời gian gốc (không AI) | 12 phút | Đề bài trường #2: tìm KB 5 phút + viết nháp 4 phút + gửi 3 phút |
| − Thời gian chờ AI phản hồi | − 0.3 phút | Claude 3.5 latency ~20 giây |
| − Thời gian người kiểm | − 3 phút | Ràng buộc đề bài: agent senior kiểm 2-4 phút (trung bình 3) |
| − Chi phí chuyển ngữ cảnh | − 0.5 phút | AI tích hợp panel Zendesk — chuyển nhẹ |
| − Thời gian sửa lại trung bình | − 0.6 phút | 20% bản nháp cần viết lại × 3 phút = 0.6 phút trung bình |
| **= Thời gian tiết kiệm thực** | **7.6 phút** | 12 − 0.3 − 3 − 0.5 − 0.6 |

Tỷ lệ thực / gộp = 7.6 / 12 = 63%, hợp với mốc tham chiếu 40-60% (hơi cao một chút — biện minh: AI tích hợp inline, chi phí chuyển ngữ cảnh thấp).

### C.2 — Lương theo giờ đã cộng phụ cấp

| Trường | Giá trị | Công thức |
|---|---|---|
| Lương cơ bản theo giờ | $20/giờ | US support agent senior |
| Hệ số phụ cấp + chi phí gián tiếp | × 1.25 | Mức bảo thủ |
| **Lương đã cộng phụ cấp** | $25/giờ | $20 × 1.25 |

### C.3 — Tỷ lệ sử dụng + Chất lượng

| Trường | Giá trị | Lý do |
|---|---|---|
| Tỷ lệ sử dụng thực tế | 65% | Đề bài: pilot dạng "khuyến khích" (không bắt buộc), UX tích hợp Zendesk inline, 1 buổi training. Mức 60-85% cho dạng có gợi ý mạnh + tích hợp tốt → 65% bảo thủ. |
| Tỷ lệ chất lượng đạt | 80% | Việc làm: sinh bản nháp. Mốc 60-80% cho dạng draft. Đề bài có 50K lịch sử ticket + RAG → cận trên 80%. Nếu KB outdated 30% có thể tụt về 75% tháng 1. |

### C.4 — Khối lượng mỗi tháng

| Trường | Giá trị | Nguồn |
|---|---|---|
| Khối lượng mỗi tháng | 3,520 ticket | Section A.2 |

### C.5 — Công thức giá trị mỗi tháng

```text
Bước 1: Giá trị tháng gộp
  = 3,520 × 7.6 × ($25 / 60)
  = $11,147

Bước 2: Điều chỉnh theo tỷ lệ sử dụng + chất lượng
  = $11,147 × 65% × 80%
  = $5,797

Bước 3: Chi phí sửa lại đã trừ trong NET (0.6 phút) → không trừ lần 2.

Giá trị thực mỗi tháng = $5,797 /tháng
```

### C.6 — ROI

```text
ROI = $5,797 / $2,803 = 2.07 : 1
```

### C.7 — Diễn giải ROI

| ROI range | Diễn giải | Hướng quyết định |
|---|---|---|
| 1.5-3:1 | Biên mỏng (marginal) | CONDITIONAL |

**Diễn giải**: ROI nằm trong vùng biên mỏng. Còn sống nhưng phụ thuộc cao vào tỷ lệ sử dụng + chất lượng. Không thể GO chắc chắn.

**Kiểm tra lại cho hợp lý**:

- Tỷ lệ sử dụng 65% có dữ liệu cứng không? Không, là ước tính. → Bảo thủ.
- Chất lượng 80% có POC không? Không. → Theo dõi tháng 1 để xác minh.
- Có quên thành phần chi phí nào không? Setup chưa phân bổ — nếu tính sẽ thêm $300-500/tháng.
- Tỷ lệ NET/Gross? 63%, hợp lý.

---

## Section D — Stress Test + Verdict

### D.1 — Bảng 5 kịch bản

| # | Kịch bản | Thay đổi | Chi phí ($/tháng) | Giá trị ($/tháng) | ROI | Trạng thái |
|---|---|---|---|---|---|---|
| 1 | Nền | (giữ nguyên) | $2,803 | $5,797 | 2.07:1 | [x] Biên mỏng |
| 2 | Dùng nhiều | Khối lượng × 3 | $8,014 | $17,391 | 2.17:1 | [x] Biên mỏng |
| 3 | Tỷ lệ sử dụng thấp | 40% (so với 65%) | $2,803 | $3,567 | 1.27:1 | [x] Yếu (dưới 1.5) |
| 4 | Chất lượng kém | 50% (so với 80%) | $2,803 | $3,623 | 1.29:1 | [x] Yếu (dưới 1.5) |
| 5 | Nhà cung cấp tăng giá | API × 2 | $2,979 | $5,797 | 1.95:1 | [x] Biên mỏng |

**Sống được X/5** (ROI ≥ 1.5): Nền, Dùng nhiều, Tăng giá → 3/5 → vùng CONDITIONAL.

### D.2 — Kịch bản xấu kết hợp

| Trường | Giá trị |
|---|---|
| Kịch bản xấu 1 | #3 Tỷ lệ sử dụng thấp (1.27:1) |
| Kịch bản xấu 2 | #5 Nhà cung cấp tăng giá (1.95:1) |
| Thay đổi kết hợp | Tỷ lệ sử dụng 40% + API × 2 |
| Chi phí kết hợp | $2,979 /tháng |
| Giá trị kết hợp | $3,567 /tháng |
| **ROI kết hợp** | **1.20:1** |
| Trạng thái | [x] Gần hoà vốn (1-1.5) |

**Lý do chọn cặp này**: hai kịch bản đại diện hai loại rủi ro khác nhau (nội bộ — tỷ lệ sử dụng + bên ngoài — giá nhà cung cấp), khả năng xảy ra đồng thời trong pilot 90 ngày là cao. Kịch bản chất lượng kém đã hurt riêng — nếu cộng thêm sẽ stress quá mức.

### D.3 — Phân tích điểm hoà vốn (break-even)

| Trường | Giá trị |
|---|---|
| Điểm hoà vốn tỷ lệ sử dụng | 31% (giữ chất lượng 80%, chi phí nền) |
| Điểm hoà vốn chất lượng | 39% (giữ tỷ lệ sử dụng 65%, chi phí nền) |
| Diễn giải | "Pilot fail nếu tỷ lệ sử dụng < 31% HOẶC chất lượng < 39%." Đây là ngưỡng cần theo dõi sát. |

Cách tính: $2,803 = $11,147 × X% × 80% → X% = $2,803 / ($11,147 × 0.8) = 31.4%.

### D.4 — Verdict

**Verdict**: [ ] GO   [x] CONDITIONAL   [ ] NO-GO

**Phát biểu verdict (3-4 câu)**:

> "CONDITIONAL GO cho Đề bài #1 — AI Support Copilot. ROI nền 2.07:1 thuộc vùng biên mỏng, sống được 3/5 kịch bản riêng lẻ (nền, dùng nhiều, tăng giá). Kịch bản xấu kết hợp (tỷ lệ sử dụng thấp + nhà cung cấp tăng giá) cho 1.20:1 — biên rất mỏng. Tiến hành pilot 90 ngày kèm 3 điều kiện cứng + giám sát hàng tuần."

### D.5 — Điều kiện đi kèm

| # | Điều kiện | Đo bằng gì | Thời hạn | Hành động nếu fail |
|---|---|---|---|---|
| 1 | Tỷ lệ sử dụng ≥ 50% trước cuối tháng 1 (mục tiêu 65% tháng 3) | Agent active / 5 agent pilot, hàng tuần | Cuối tháng 1 | Tạm dừng pilot, training tăng cường |
| 2 | Chất lượng ≥ 70% (mục tiêu 80%) | Lấy ngẫu nhiên 50 bản nháp/tuần, % dùng được không cần viết lại nhiều | Hàng tuần | Tinh chỉnh prompt + index lại RAG |
| 3 | Khoá giá API với Anthropic 6 tháng HOẶC chuẩn bị sẵn mô hình dự phòng (GPT-4o-mini) | Hợp đồng + test fallback | Trước khi pilot bắt đầu | Chặn pilot cho đến khi khoá được giá |
| 4 | Chi phí mỗi việc ≤ $0.80 (hiệu dụng) | Log billing hàng tuần | Hàng tuần | Chuyển sang GPT-4o-mini cho phần FAQ tier-1 |
| 5 | Chi phí tháng ≤ $3,000 (cổng cứng) | Dashboard tài chính | Hàng tháng | Báo CTO, dừng pilot tháng sau |

### D.6 — Chỉ số theo dõi

| Chỉ số | Tần suất | Nguồn | Ngưỡng |
|---|---|---|---|
| Tỷ lệ sử dụng | Hàng tuần | Log Zendesk app | ≥ 50% |
| Chi phí mỗi việc | Hàng tuần | Billing Anthropic + Pinecone | ≤ $0.80 |
| Tỷ lệ chất lượng | Hàng tuần | Mẫu ngẫu nhiên 50 bản nháp | ≥ 70% |
| Mức hài lòng của agent | Hàng tháng | Khảo sát 5 agent | NPS ≥ 20 |
| Tổng chi phí tháng | Hàng tháng | Dashboard tài chính | ≤ $3,000 |

### D.7 — Trigger dừng / xoay hướng

- Trigger 1: Tỷ lệ sử dụng < 40% trong 30 ngày liên tiếp → tạm dừng pilot, training tăng cường.
- Trigger 2: Chi phí mỗi việc > $1.20 trong 2 tuần liên tiếp → chuyển sang GPT-4o-mini.
- Trigger 3: Chất lượng < 50% trong 30 ngày → tinh chỉnh prompt + index lại RAG, hoặc tạm dừng.
- Trigger 4: Sự cố tuân thủ (1 bản nháp gửi đi mà chưa được kiểm do lỗi AI tự gửi) → dừng ngay, root-cause review.

### D.8 — Thay đổi cần làm (không áp dụng — verdict không phải NO-GO)

---

## Section D — 3 nhận xét chính

1. **Kịch bản hurt nhất**: Tỷ lệ sử dụng thấp (1.27:1) và Chất lượng kém (1.29:1) gần ngang nhau. Cả hai đều kéo ROI xuống vùng yếu vì ROI nền vốn đã thấp.
2. **Pattern kết hợp**: khi rủi ro nội bộ (sử dụng) + bên ngoài (nhà cung cấp) xảy ra cùng lúc, ROI rơi xuống 1.20 — sát điểm hoà vốn. Mọi điều kiện ở D.5 đều quan trọng.
3. **Điều người mua cần nhớ**: tỷ lệ sử dụng là biến nhạy nhất + dễ kiểm soát nhất. Đầu tư training + onboarding > đầu tư đổi mô hình. Ngưỡng 50% tháng 1 là "sống chết".

---

## Nhận xét xuyên các Section

1. **Cấu trúc chi phí**: người kiểm (87%) chi phối, không phải API (6%). Đây là pattern phổ biến khi đề bài có ràng buộc tuân thủ — đừng tối ưu nhầm hướng (đổi mô hình rẻ hơn không cứu nổi).
2. **Độ nhạy giá trị**: tỷ lệ sử dụng × chất lượng nhân với nhau theo cấp số. 65% × 80% = 52% hiệu dụng. Nếu cả hai tụt xuống 40% × 50% = 20% hiệu dụng → giá trị sụp 60%.
3. **Nhận xét quyết định**: kết hợp xấu nhất 1.20:1 sát điểm hoà vốn 1.0:1 → biên an toàn rất mỏng. Mọi điều kiện ở D.5 là điều kiện sống chết, không phải "tốt thì có".

---

## Lưu ý cuối

File này là **ví dụ tham chiếu**, không phải template để dán đè. Nhóm khác:

- Có thể có verdict GO hoặc NO-GO tuỳ đề bài.
- Số sẽ khác hoàn toàn — Đề bài #2 (Content Moderator) có khối lượng × 100, chi phí API chi phối.
- Mỗi % phải tự viết lý do theo ngữ cảnh đề bài, không copy.

Đọc xong file này → quay lại `worksheet/00-context.md` để bắt đầu Lab với đề bài của nhóm.
