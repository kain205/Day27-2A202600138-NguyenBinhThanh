---
artifact: 2 — Chốt cách định giá + chọn đơn vị khách trả tiền
buoc: 2 — Định giá + Giá trị / ROI
phase: Chốt cách định giá cụ thể + đơn vị khách trả tiền (value metric) + kiểm tra rủi ro "ngại dùng vì sợ tốn"
thoi-gian: 10 phút
input: 1-attribution-autonomy.md + prompts/04-pricing-model-choice.md
nop-cuoi: Không — đây là file trung gian (Section B của `04-FINAL-economics-sheet.md` mới là bản nộp)
---

# 2 — Chốt cách định giá + đơn vị khách trả tiền

**Mục tiêu**: nhóm có cách định giá tự nhiên từ ma trận ở file 1, giờ chốt **một cách định giá cụ thể có con số**, chọn **đơn vị khách trả tiền cho**, và kiểm tra một rủi ro hay bị bỏ quên: khách ngại dùng AI vì sợ bị tính tiền nhiều (gọi là *Usage Anxiety*).

Vì sao quan trọng: ô trên ma trận mới cho biết "kiểu" định giá. Còn con số bao nhiêu, đơn vị tính là gì, người mua có chấp nhận không — phải chốt ở bước này. Định giá đẹp trên giấy nhưng người mua không hiểu, hoặc người dùng không dám dùng → giá trị thực rơi.

**Quy tắc**: đơn vị khách trả tiền phải qua **CAMP test** — Countable (đếm được) / Aligned (gắn với giá trị AI tạo ra) / Meaningful (người mua hiểu) / Predictable (có thể dự đoán được).

---

## Tổng thời gian 10 phút

| Phần | Thời gian | Việc cần làm |
|---|---|---|
| A | 3 phút | Chốt cách định giá cụ thể + con số |
| B | 3 phút | Chọn đơn vị khách trả tiền + CAMP test |
| C | 2 phút | Xác định người mua + lý do mua bây giờ |
| D | 2 phút | Kiểm tra rủi ro Usage Anxiety |

---

## Phần A — Chốt cách định giá cụ thể

### Bốn nhóm cách định giá

Đọc lướt bảng sau để nhớ lại từ file 1, rồi chọn cho đề bài nhóm.

| Cách định giá | Mô tả | Hợp khi nào | Ví dụ thật |
|---|---|---|---|
| **Seat / Cố định** | $X mỗi người dùng mỗi tháng | Autonomy thấp + Attribution thấp | Grammarly $12/người/tháng, Slack AI $7/người |
| **Usage-based** | $X mỗi đơn vị khối lượng dùng | Autonomy cao + Attribution thấp | OpenAI API $0.50/1M token, AWS theo lượt gọi |
| **Outcome-based** | $X mỗi kết quả thực tế | Autonomy cao + Attribution cao | Intercom Fin $0.99/ticket xử lý xong, Chargeflow theo vụ thắng |
| **Hybrid** | Seat cố định + thêm tiền theo khối lượng (hoặc gói tier theo kết quả) | Trộn (Autonomy trung bình, Attribution trung bình–cao) | Cursor $20 + credit, Clay gói $149/$349/$800 |

### Cách định giá nhóm chốt cho đề bài

Trước khi điền, tự hỏi:

- Cách định giá tự nhiên theo ma trận (từ file 1) là gì?
- Có lý do gì để chọn cách khác không?
- Nếu chọn Hybrid, phần Seat bao nhiêu, phần thêm tính theo gì?

**Tên cách định giá**:

```text
(điền vào đây)
```

**Cấu trúc giá cụ thể có con số** *(ví dụ format: "$X mỗi Y, kèm Z")*:

```text
(điền vào đây)
```

**Vì sao chọn cách này thay vì 3 cách kia** *(1-3 câu)*:

```text
(điền vào đây)
```

---

## Phần B — Đơn vị khách trả tiền (value metric)

Đơn vị khách trả tiền cho = thứ khách hàng nhìn vào hóa đơn và hiểu "tôi trả tiền cho cái này".

Ví dụ:

- Intercom Fin: đơn vị = "1 ticket xử lý xong".
- OpenAI API: đơn vị = "1 triệu token".
- Cursor: đơn vị = "1 người dùng/tháng" + "1 credit".

### Đơn vị khách trả tiền của nhóm

Trước khi viết, tự hỏi:

- Khách hàng đang trả tiền cho thứ gì cụ thể mà AI làm ra?
- Họ có thể đếm thứ đó không? Có hiểu nó là gì không?
- Thứ đó có gắn trực tiếp với giá trị AI tạo ra không?

**Đơn vị khách trả tiền**:

```text
(điền vào đây — vd: 1 ticket xử lý xong / 1 hợp đồng đọc xong / 1 người dùng/tháng)
```

### CAMP test — kiểm tra đơn vị đã chọn

Đơn vị tốt phải qua cả 4 câu kiểm tra:

| Câu kiểm tra | Có / Không | Bằng chứng |
|---|---|---|
| **C — Countable** (đếm được, không cãi nhau) | _ _ _ | _ _ _ |
| **A — Aligned** (gắn trực tiếp với giá trị AI, không phải việc người làm) | _ _ _ | _ _ _ |
| **M — Meaningful** (người mua hiểu và thấy quan trọng) | _ _ _ | _ _ _ |
| **P — Predictable** (khách dự đoán được chi phí mỗi tháng) | _ _ _ | _ _ _ |

Cả 4 = Có → đơn vị hợp lệ. Nếu có một câu = Không, sửa lại đơn vị trước khi sang phần C.

### Những lỗi hay mắc khi chọn đơn vị khách trả tiền

| Lỗi | Vì sao sai |
|---|---|
| **Đơn vị quá kỹ thuật** *(vd: "lượt gọi API")* | Người mua (giám đốc, trưởng phòng) không quan tâm; họ quan tâm "ticket xử lý xong" |
| **Đơn vị không đếm được** *(vd: "chất lượng tốt hơn")* | Không có con số, không thể ra hóa đơn |
| **Đơn vị không gắn với AI** *(vd: "số nhân viên trong đội")* | AI không phải là lý do đội to/nhỏ |
| **Đơn vị khó dự đoán** *(vd: "lượt tương tác")* | Khách không biết tháng tới sẽ tốn bao nhiêu → ngại ký hợp đồng |

---

## Phần C — Người mua + Lý do mua bây giờ

### Ai là người ra quyết định mua?

Đọc đề bài, trường "Quyết định cần ra" cho biết ai là người mua trong đề bài.

**Vai trò người mua** *(vd: Giám đốc CNTT / Trưởng phòng Support / Phó tổng phụ trách An toàn / Trưởng nhóm Cung ứng)*:

```text
(điền vào đây)
```

### Vì sao họ quyết định mua **bây giờ**, không phải năm sau?

Trước khi viết, tự hỏi:

- Điểm đau trong đề bài (trường 3) đang gây thiệt hại gì cụ thể?
- Việc này có cấp bách không, hay là "có thì tốt"?
- Họ đang cân nhắc giải pháp nào khác *(tuyển thêm người / thuê ngoài / chấp nhận điểm đau)*?

**Điểm đau chính khiến họ phải hành động**:

```text
(điền vào đây)
```

**Mức cấp bách** *(bắt buộc làm ngay / nên có / có thì tốt)*:

```text
(điền vào đây)
```

**Giải pháp thay thế họ đang cân nhắc**:

```text
(điền vào đây)
```

### Cách định giá nhóm chọn có hợp với người mua không?

Đối chiếu nhanh:

- Seat → chi phí dự đoán được → tài chính thường thích.
- Usage → chi phí biến động → tài chính cần đặt mức trần.
- Outcome → dễ bảo vệ ROI → cấp điều hành thường thích.
- Hybrid → phức tạp hơn để bán → cần giải thích kỹ.

**Mức độ hợp với người mua** *(tốt / trung bình / yếu)*:

```text
(điền vào đây)
```

**Lý do**:

```text
(điền vào đây)
```

---

## Phần D — Kiểm tra Usage Anxiety

### Usage Anxiety là gì

Khi cách định giá có yếu tố tính theo khối lượng dùng, người dùng có thể **tự hạn chế dùng** vì sợ làm bill tăng. AI không được dùng thật → không tạo ra giá trị thật → ROI thực tế thấp hơn ROI tính toán.

Ví dụ: Cursor có hệ thống credit. Khi credit sắp hết, có hộp thoại "credit thấp, nâng cấp?" → người dùng ngại bấm tiếp → giá trị AI bị nén lại.

### Đề bài nhóm có rủi ro Usage Anxiety không?

Tự đánh giá 4 câu sau:

| Câu hỏi | Có / Không |
|---|---|
| Cách định giá có yếu tố tính theo khối lượng dùng? | _ _ _ |
| Người dùng cuối có nhìn thấy chi phí mỗi lần dùng AI? | _ _ _ |
| Người dùng có quyền tự đặt giới hạn (cap) không? | _ _ _ |
| Có giải pháp miễn phí mà người dùng có thể chuyển sang? | _ _ _ |

**Mức rủi ro Usage Anxiety** *(thấp / trung bình / cao)*:

```text
(điền vào đây)
```

### Nếu rủi ro trung bình hoặc cao — đề xuất cách giảm

Trước khi viết, suy nghĩ 3 hướng:

- Có thể đưa khối lượng vào gói cố định (kiểu Cursor) để người dùng không thấy từng đồng?
- Có thể giấu chi phí từng lần (chỉ hiện "credit còn lại") không?
- Có thể cho gói thử miễn phí 10 lượt/tháng để giảm e ngại không?

**Cách giảm rủi ro nhóm đề xuất**:

```text
(điền vào đây — nếu rủi ro thấp, ghi "không cần")
```

---

## Phần E — Bảng tổng hợp Section B (để chép sang FINAL)

Sau khi xong các phần trên, điền bảng tổng hợp này. Đây là dữ liệu sẽ dán vào Section B của `3-FINAL-pricing-value-roi.md`.

| Trường | Giá trị |
|---|---|
| Autonomy (từ file 1) | _ _ _ |
| Attribution (từ file 1) | _ _ _ |
| Ô trên ma trận (từ file 1) | _ _ _ |
| Cách định giá đã chốt | _ _ _ |
| Cấu trúc giá cụ thể | _ _ _ |
| Đơn vị khách trả tiền | _ _ _ |
| Người mua | _ _ _ |
| Sản phẩm thật so sánh (từ file 1) | _ _ _ |
| Mức rủi ro Usage Anxiety | _ _ _ |
| Cách giảm rủi ro | _ _ _ |

---

## Phần F — Kiểm tra trước khi sang `3-FINAL-pricing-value-roi.md`

- [ ] Cách định giá rõ ràng (1 trong 4 nhóm) + có con số cụ thể
- [ ] Đơn vị khách trả tiền qua được CAMP test (cả 4 = Có)
- [ ] Người mua cụ thể (vai trò + lấy từ trường 6 của đề bài)
- [ ] Có 1 sản phẩm thật cùng cách định giá để đối chiếu (từ file 1)
- [ ] Mức Usage Anxiety đã đánh giá thấp / trung bình / cao + có cách giảm nếu cần

---

## Những lỗi hay mắc

| Đừng làm | Nên làm |
|---|---|
| "Định giá tùy theo nhu cầu" | Chốt **một** cách định giá + giá đề xuất cụ thể |
| Đơn vị khách trả tiền = "lượt dùng AI" | Cụ thể: "1 ticket xử lý xong", "1 hợp đồng đọc" |
| Quên người mua | Mọi cách định giá phải có người mua cụ thể từ trường 6 của đề bài |
| Định giá không gắn với chi phí ở Section A | Giá đề xuất phải > chi phí mỗi đơn vị + phần lãi |
| Bỏ qua Usage Anxiety | Mọi cách định giá có yếu tố theo lượng đều phải kiểm tra |

---

Sang bước tiếp theo: mở `3-FINAL-pricing-value-roi.md` để tính giá trị mỗi tháng + ROI và chốt Section B + C của bản nộp.
