---
artifact: 1 — Đặt sản phẩm trên ma trận Attribution × Autonomy
buoc: 2 — Định giá + Giá trị / ROI
phase: Đặt vị trí trên ma trận 2×2 để biết cách định giá nào hợp tự nhiên
thoi-gian: 15 phút
input: 00-context.md + đề bài + 01-cost-model/3-FINAL-cost-model.md + prompts/03-attribution-autonomy.md
nop-cuoi: Không — đây là file trung gian (Section B của `04-FINAL-economics-sheet.md` mới là bản nộp)
---

# 1 — Đặt sản phẩm trên ma trận Attribution × Autonomy

**Mục tiêu**: trước khi chọn cách định giá, nhóm phải xác định 2 đặc tính của AI trong đề bài — *Autonomy* (AI có làm tự chủ không) và *Attribution* (giá trị AI tạo ra có rõ ràng không). Hai trục này quyết định cách định giá nào tự nhiên hợp với sản phẩm.

Vì sao quan trọng: cách định giá không tự nhiên xuất hiện. Nó là **hệ quả** của vị trí AI trên ma trận. Đặt sản phẩm vào sai ô → cách định giá lệch với cách giá trị tạo ra → khách không hiểu vì sao họ trả tiền.

**Quy tắc**: không có vị trí cụ thể trên ma trận = không có lý do để bảo vệ cách định giá.

---

## Tổng thời gian 15 phút

| Phần | Thời gian | Việc cần làm |
|---|---|---|
| A | 4 phút | Hiểu 2 trục — Autonomy và Attribution |
| B | 5 phút | Trả lời 2 câu hỏi cho đề bài của nhóm |
| C | 3 phút | Đặt vị trí trên ma trận + chọn ô |
| D | 3 phút | Đối chiếu với một sản phẩm thật cùng ô |

---

## Phần A — Hiểu 2 trục của ma trận

### Trục Autonomy (dọc) — AI có làm tự chủ không?

**Câu hỏi**: Khi AI chạy xong một lần, có cần người duyệt rồi mới ra kết quả không, hay AI tự đẩy thẳng ra ngoài?

- **Autonomy thấp** — AI gợi ý, người là người quyết định cuối.
  - Grammarly đưa ra gợi ý sửa câu, người gõ chữ chọn nhận hay bỏ.
  - GitHub Copilot viết nháp đoạn mã, lập trình viên sửa rồi mới commit.
  - Trợ lý trả lời cho đội support đề xuất câu trả lời, nhân viên duyệt rồi mới gửi.

- **Autonomy cao** — AI làm xong việc và đẩy thẳng đầu ra, người không xen vào (hoặc chỉ kiểm tra theo mẫu).
  - OpenAI API tự phân loại nội dung và lưu nhãn.
  - Intercom Fin tự trả lời người dùng cuối, không qua nhân viên.
  - AWS Auto Scaling tự quyết khi nào tăng/giảm máy chủ.

### Trục Attribution (ngang) — Giá trị AI tạo ra có rõ không?

**Câu hỏi**: Khi nhìn vào một kết quả tốt, có thể nói rõ "AI làm ra cái này" không, hay nó hòa lẫn vào việc của cả đội?

- **Attribution thấp** — Khó tách phần AI ra khỏi phần đội ngũ làm.
  - AI giúp đội viết tài liệu nhanh hơn → kết quả là "đội viết tốt", không phải "AI viết tốt".
  - Slack AI tóm tắt hội thoại → khó nói "AI là lý do chốt được đơn".

- **Attribution cao** — Thấy rõ AI là người tạo ra kết quả cụ thể đó.
  - Intercom Fin tự xử lý xong 1 ticket → rõ ràng AI giải quyết.
  - Chargeflow thắng 1 vụ tranh chấp thẻ → rõ ràng AI thắng.
  - DALL-E tạo ra 1 hình ảnh → rõ ràng AI tạo.

---

## Phần B — Trả lời 2 câu hỏi cho đề bài nhóm

### Câu hỏi 1: Autonomy của AI trong đề bài

Trước khi quyết, tự hỏi:

- AI làm gì một mình từ đầu đến cuối?
- Người làm gì ở khâu cuối, sau khi AI đã chạy xong?
- Đề bài có ràng buộc "100% người phải duyệt" không?
- AI có được tự gửi đầu ra cho khách / tự thay đổi hệ thống thật không?

**Kết luận: AI trong đề bài thuộc Autonomy thấp hay cao?**

```text
(điền vào đây — chọn thấp / cao)
```

**Giải thích trong 1-2 câu vì sao chọn vậy**:

```text
(điền vào đây)
```

### Câu hỏi 2: Attribution của AI trong đề bài

Trước khi quyết, tự hỏi:

- Khi AI làm xong 1 đơn vị việc (1 ticket / 1 cảnh báo / 1 hợp đồng), có thể nói rõ "cái này là AI làm" không?
- Hay AI chỉ là một bước trong quy trình dài, khó tách phần đóng góp?
- Khách hàng có **thấy được** AI tạo ra giá trị, hay AI giấu mặt sau đội ngũ?

**Kết luận: AI trong đề bài thuộc Attribution thấp hay cao?**

```text
(điền vào đây — chọn thấp / cao)
```

**Giải thích trong 1-2 câu**:

```text
(điền vào đây)
```

---

## Phần C — Đặt vị trí trên ma trận

Đây là ma trận Attribution × Autonomy với 4 ô. Mỗi ô gợi ý một cách định giá tự nhiên:

```text
                Attribution thấp             Attribution cao

Autonomy thấp   Seat / Cố định                Hybrid (Seat + Credit)
(người quyết)   Grammarly                    Cursor: $20 + credit
                Slack AI                     Canva: $15 + 500 credit
                                             Clay: gói $149-$800

Autonomy cao    Usage-based                  Outcome-based
(AI tự làm)     OpenAI API                   Intercom Fin: $0.99/lần xử lý
                Dịch vụ AI của AWS           Chargeflow: theo vụ thắng
                Pinecone                     Zendesk: $1.50/ticket xong
```

### Vị trí của đề bài nhóm

- **Trục Autonomy**:

```text
(điền vào đây — thấp / cao)
```

- **Trục Attribution**:

```text
(điền vào đây — thấp / cao)
```

- **Ô nhóm chọn** *(một trong 4 ô)*:

```text
(điền vào đây)
```

### Cách định giá tự nhiên theo ma trận

```text
(điền vào đây — Seat / Usage / Outcome / Hybrid)
```

---

## Phần D — Đối chiếu với một sản phẩm thật

Tìm **một sản phẩm AI thật** đang nằm trong cùng ô với đề bài nhóm. Đối chiếu để kiểm tra xem vị trí nhóm chọn có hợp lý không.

Trước khi chọn sản phẩm so sánh, tự hỏi:

- Sản phẩm này có giải quyết bài toán tương tự đề bài không?
- Họ đặt AI ở Autonomy nào, Attribution nào?
- Họ đang định giá theo cách gì?

**Sản phẩm thật nhóm chọn để so sánh**:

```text
(điền vào đây — vd: tên sản phẩm + 1 câu mô tả họ làm gì)
```

**Họ nằm ở ô nào trên ma trận**:

```text
(điền vào đây)
```

**Họ định giá theo cách gì** *(nếu biết, ghi số cụ thể)*:

```text
(điền vào đây)
```

**Có khớp với ô nhóm chọn cho đề bài không?**

```text
(điền vào đây — khớp / không khớp; nếu không, suy nghĩ lại vị trí trên ma trận)
```

---

## Ví dụ: cách các đề bài hay rơi vào ô nào

*(Đọc tham khảo, không copy thẳng — đề bài của nhóm có thể khác.)*

- **Trợ lý cho support** — Autonomy thấp + Attribution trung bình → ô Hybrid. Sản phẩm tương tự: Cursor, GitHub Copilot.
- **Bộ lọc nội dung** với ràng buộc 100% người duyệt — Autonomy thấp + Attribution thấp → ô Seat. Sản phẩm tương tự: nhiều công cụ bundle theo seat.
- **Hệ thống phân loại đầu vào y tế** — Autonomy thấp + Attribution trung bình → ô Hybrid leaning Seat. Sản phẩm tương tự: AI tích hợp trong Epic EHR.
- **Trợ lý đọc hợp đồng pháp lý** — Autonomy thấp + Attribution cao (rõ AI gắn cờ điểm rủi ro) → Hybrid (Seat + theo lượng). Sản phẩm tương tự: Harvey, Kira.
- **AI viết email cho sale** — Autonomy thấp + Attribution trung bình → ô Hybrid. Sản phẩm tương tự: Clay, Lavender, Apollo.io.
- **Trợ lý review code** — Autonomy thấp + Attribution cao (rõ AI tìm ra lỗi nào) → Hybrid (Seat + theo PR). Sản phẩm tương tự: Codium, Sourcegraph Cody.
- **Dự báo tồn kho** — Autonomy thấp + Attribution cao → Seat hoặc Hybrid. Sản phẩm tương tự: Blue Yonder, o9.
- **AI chấm bài luận** — Autonomy thấp + Attribution cao → Hybrid (Seat + theo lượt chấm). Sản phẩm tương tự: GradeScope, Turnitin.
- **AI xử lý yêu cầu bảo hiểm** — Autonomy thấp + Attribution cao → Outcome-based (theo claim xử lý xong). Sản phẩm tương tự: Tractable, Lemonade AI.
- **AI viết mô tả bất động sản** — Autonomy thấp + Attribution cao → Hybrid (Seat + theo listing). Sản phẩm tương tự: HouseSigma AI, ListingDojo.

---

## Phần E — Khi đề bài "nửa cao nửa thấp"

Một số đề bài không dứt khoát thấp/cao. Cách xử lý:

- **Autonomy "trung bình"** *(vd: AI làm nháp nhưng 80% trường hợp cần người duyệt)* → coi là Autonomy thấp **nếu** việc người duyệt là **ràng buộc cứng**, không phải tùy chọn.
- **Attribution "trung bình"** *(vd: AI gắn cờ điểm trong hợp đồng, nhưng luật sư là người chốt danh sách điểm cần sửa)* → vẫn coi là Attribution cao **vì** AI vẫn có đầu ra rõ ràng cho 1 hợp đồng.

Nếu đề bài nhóm nằm "giữa":

- *Autonomy thấp + Attribution trung bình* → Hybrid nghiêng Seat (kiểu Cursor: $20 + credit).
- *Autonomy thấp + Attribution cao* → Hybrid (Seat + theo lượng đầu ra) (kiểu Clay: gói tier theo lượng).

**Đề bài nhóm có rơi vào "giữa" không?** Nếu có, nhóm nghiêng về hướng nào và vì sao?

```text
(điền vào đây — nếu không rơi vào "giữa", ghi "không")
```

---

## Phần F — Kiểm tra trước khi sang `2-pricing-model-choice.md`

- [ ] Đã chọn rõ Autonomy thấp / cao + giải thích 1-2 câu
- [ ] Đã chọn rõ Attribution thấp / cao + giải thích 1-2 câu
- [ ] Đã đặt đề bài vào **một** ô cụ thể trên ma trận (không "ở giữa cả 4 ô")
- [ ] Đã ghi cách định giá tự nhiên theo ma trận
- [ ] Đã tìm 1 sản phẩm thật cùng ô để đối chiếu

---

## Câu hỏi mở để mang sang `2-pricing-model-choice.md`

Trước khi sang file tiếp theo, nhóm tự ghi 2-3 câu hỏi đang băn khoăn:

```text
1. (điền vào đây — vd: cách định giá tự nhiên có phù hợp với người mua trong đề bài không?)
2.
3.
```

---

Sang bước tiếp theo: mở `2-pricing-model-choice.md` để chốt cách định giá cụ thể + chọn đơn vị khách trả tiền + kiểm tra rủi ro "ngại dùng AI vì sợ tốn".
