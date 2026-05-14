---
artifact: 3 — FINAL — Định giá + Giá trị + ROI (Section B + C của Economics Sheet)
buoc: 2 — Định giá + Giá trị / ROI
phase: Chốt Section B + C của bản nộp cuối
thoi-gian: 15 phút
input: 1-attribution-autonomy.md + 2-pricing-model-choice.md + prompts/05-value-formula.md + prompts/06-roi-analysis.md
nop-cuoi: Có — Section B + C sẽ được nộp trong `04-FINAL-economics-sheet.md`
---

# 3 — FINAL — Định giá + Giá trị + ROI

**Mục tiêu**: gộp kết quả từ 2 file trước (cách định giá, đơn vị khách trả tiền) với phép tính giá trị mỗi tháng và ROI. Đầu ra là Section B + Section C của bản nộp cuối — sẵn sàng chép sang `04-FINAL-economics-sheet.md`.

Vì sao quan trọng: ROI là con số duy nhất người mua hỏi đầu tiên. Nhưng ROI dễ thổi phồng nếu nhóm:

- Dùng thời gian tiết kiệm thô (Gross) thay vì thời gian tiết kiệm thật (NET — đã trừ thời gian chờ AI, người duyệt, đổi cửa sổ làm việc, sửa lại khi AI sai).
- Cho tỷ lệ sử dụng thực tế quá cao (vd: 95% — gần như không có thật).
- Cho chất lượng AI quá cao (vd: 95% — chỉ có ở việc đơn giản).

**Quy tắc**:

- Mỗi % trong công thức phải có lý do giải thích (vd: tỷ lệ sử dụng 70% vì lý do A, B).
- ROI = Giá trị mỗi tháng / Chi phí mỗi tháng. Phải là **một số cụ thể**, không "khoảng".
- Nếu tỷ lệ sử dụng > 80% hoặc chất lượng > 90% → bắt buộc có lý do mạnh, không được tự đặt.

---

## Tổng thời gian 15 phút

| Phần | Thời gian | Việc cần làm |
|---|---|---|
| B (chép từ file 1+2) | 3 phút | Dán tổng hợp Section B vào bảng |
| C.1 | 3 phút | Tính NET thời gian tiết kiệm mỗi việc |
| C.2-C.4 | 3 phút | Mức lương tính đủ + tỷ lệ sử dụng + chất lượng + khối lượng |
| C.5 | 3 phút | Tính giá trị mỗi tháng theo công thức |
| C.6-C.7 | 3 phút | Tính ROI + tự kiểm tra hợp lý |

---

## Thông tin nhóm

**Số đề bài + tên ngắn**:

```text
(điền vào đây)
```

**Tên 2 thành viên + mã học viên**:

```text
(điền vào đây)
```

**Ngày tính** *(YYYY-MM-DD)*:

```text
(điền vào đây)
```

**Phiên bản**: v1

---

## Section B — Định giá / Cách bán

### B.1 — Vị trí trên ma trận Attribution × Autonomy

*(Chép từ file `1-attribution-autonomy.md`)*

| Trường | Giá trị | Giải thích 1 câu |
|---|---|---|
| Autonomy *(thấp / cao)* | _ _ _ | _ _ _ |
| Attribution *(thấp / cao)* | _ _ _ | _ _ _ |
| Ô trên ma trận | _ _ _ | — |

### B.2 — Cách định giá

*(Chép từ file `2-pricing-model-choice.md`)*

| Trường | Giá trị |
|---|---|
| Cách định giá đã chốt | _ _ _ |
| Cấu trúc giá cụ thể *(có con số)* | _ _ _ |
| Đơn vị khách trả tiền | _ _ _ |
| Vai trò người mua | _ _ _ |
| Lý do người mua phải hành động bây giờ | _ _ _ |

### B.3 — Sản phẩm thật để so sánh

| Trường | Giá trị |
|---|---|
| Tên sản phẩm so sánh | _ _ _ |
| Cách họ định giá *(số cụ thể)* | _ _ _ |
| Vì sao đây là so sánh phù hợp *(1 câu)* | _ _ _ |

### B.4 — Kiểm tra Usage Anxiety

| Trường | Giá trị |
|---|---|
| Mức rủi ro Usage Anxiety *(thấp / trung bình / cao)* | _ _ _ |
| Cách giảm rủi ro *(nếu trung bình hoặc cao)* | _ _ _ |

---

## Section C — Giá trị / ROI

### C.1 — Thời gian tiết kiệm NET mỗi việc

NET = thời gian tiết kiệm **thật**, sau khi đã trừ các phần overhead AI mang lại.

Trước khi điền, mở đề bài và lấy ra: "thời gian xử lý một việc khi chưa có AI" (trường 2 của đề bài).

| Thành phần | Giá trị | Lý do |
|---|---|---|
| Thời gian ban đầu *(chưa có AI)* | _ _ _ phút | Lấy từ trường 2 đề bài |
| − Thời gian chờ AI phản hồi | − _ _ _ phút | Độ trễ một lần AI tính (thường 5-30 giây) |
| − Thời gian người duyệt đầu ra AI | − _ _ _ phút | Nếu đề bài có ràng buộc người phải kiểm tra |
| − Thời gian đổi cửa sổ làm việc | − _ _ _ phút | Người dùng chuyển giữa AI và công cụ chính |
| − Thời gian sửa lại khi AI sai *(trung bình)* | − _ _ _ phút | Phụ thuộc vào chất lượng AI |
| **= NET thời gian tiết kiệm mỗi việc** | _ _ _ phút | Cộng/trừ ra |

**Kiểm tra hợp lý**: NET thường = 40-60% của thời gian ban đầu. Nếu NET > 80% thời gian ban đầu → có thể đã quên một phần overhead. Tự kiểm tra lại.

```text
NET / Thời gian ban đầu = _ _ _ %
```

### C.2 — Mức lương tính đủ một giờ

Mức lương tính đủ = lương cơ bản × hệ số cho thuế, bảo hiểm, văn phòng, công cụ làm việc.

| Trường | Giá trị | Cách tính |
|---|---|---|
| Lương cơ bản một giờ | $_ _ _ / giờ | Lương cơ bản (có thể quy đổi từ lương tháng) |
| Hệ số tính đủ | × 1.3-1.5 | Cộng phụ cấp, thuế, văn phòng, công cụ |
| **Mức lương tính đủ** | $_ _ _ / giờ | Lương cơ bản × hệ số |

**Hệ số nhóm chọn**:

```text
(điền vào đây — và 1 câu lý do)
```

### C.3 — Tỷ lệ sử dụng thực tế + Hệ số chất lượng

| Trường | Giá trị | Lý do *(bắt buộc viết)* |
|---|---|---|
| Tỷ lệ sử dụng thực tế *(adoption)* | _ _ _ % | _ _ _ |
| Hệ số chất lượng AI | _ _ _ % | _ _ _ |

Trước khi điền, đọc tham khảo các khoảng phổ biến:

- **Tỷ lệ sử dụng**:
  - Công cụ bắt buộc dùng: 60-85%
  - Tùy chọn: 30-60%
  - Hành vi mới hoàn toàn: 20-50%
  - Có thưởng cho người thử: 50-80% (thường chỉ trong giai đoạn thử nghiệm)

- **Chất lượng AI**:
  - Phân loại / gán nhãn: 80-95%
  - Viết nháp: 60-80%
  - Tóm tắt: 70-85%
  - Sáng tạo / dài: 50-70%
  - Suy luận phức tạp: 40-65%

**Cảnh báo**:

- Tỷ lệ sử dụng > 80% → phải có dữ liệu hoặc lý do mạnh, không tự đặt.
- Chất lượng > 85% → phải có dữ liệu từ thử nghiệm hoặc benchmark.
- Cả hai > 90% → gần như chắc chắn đang thổi phồng.

### C.4 — Khối lượng mỗi tháng

*(Lấy từ Section A — Phần C.2 của `01-cost-model/1-usage-unit.md`)*

| Trường | Giá trị | Nguồn |
|---|---|---|
| Khối lượng mỗi tháng *(số việc)* | _ _ _ | Section A.2 (Cost Model) |

### C.5 — Công thức giá trị mỗi tháng

Công thức chia làm 3 bước. Điền số rồi tính tay (hoặc Google Sheets).

```text
Bước 1 — Giá trị tổng (chưa điều chỉnh)

  Giá trị tổng = Khối lượng/tháng × NET thời gian tiết kiệm × (Lương tính đủ / 60)
              = _ _ _ × _ _ _ phút × ($_ _ _ / 60)
              = $_ _ _ /tháng

Bước 2 — Điều chỉnh theo tỷ lệ sử dụng và chất lượng

  Giá trị điều chỉnh = Giá trị tổng × Tỷ lệ sử dụng × Chất lượng
                    = $_ _ _ × _ _ _ % × _ _ _ %
                    = $_ _ _ /tháng

Bước 3 — Trừ chi phí sửa lại (nếu chưa nằm trong NET)

  *(Nếu thời gian sửa lại đã trừ trong NET ở Phần C.1 — bỏ qua bước này.
   Nếu chưa, trừ thêm chi phí sửa lại ở đây.)*

  Trừ chi phí sửa lại:
  − $_ _ _

= GIÁ TRỊ NET MỖI THÁNG: $_ _ _ /tháng
```

### C.6 — Tính ROI

ROI = Giá trị mỗi tháng / Chi phí mỗi tháng *(Section A.6 của Cost Model)*.

```text
ROI = Giá trị mỗi tháng / Chi phí mỗi tháng
    = $_ _ _ / $_ _ _
    = _ _ _ : 1
```

### C.7 — Giải thích ROI

| Khoảng ROI | Ý nghĩa | Xu hướng quyết định |
|---|---|---|
| > 5:1 | Mạnh | Có thể GO *(nhưng kiểm tra có thổi phồng không)* |
| 3-5:1 | Vững | Có thể GO |
| 1.5-3:1 | Mong manh | CONDITIONAL |
| 1-1.5:1 | Yếu | CONDITIONAL với điều kiện chặt *(hoặc NO-GO nếu kịch bản xấu < 1:1)* |
| < 1:1 | Âm | NO-GO |
| > 20:1 | Có thể thổi phồng | Kiểm tra lại các giả định |

**ROI của nhóm**:

```text
(điền số cụ thể, vd: 3.2 : 1)
```

**Khoảng ROI thuộc nhóm nào**:

```text
(điền vào đây)
```

### C.8 — Tự kiểm tra hợp lý

Trước khi sang stress test, tự hỏi 4 câu sau và viết câu trả lời thật:

| Câu hỏi | Trả lời |
|---|---|
| Tỷ lệ sử dụng nhóm chọn có quá lạc quan không? | _ _ _ |
| Hệ số chất lượng nhóm chọn có quá lạc quan không? | _ _ _ |
| Có quên thành phần chi phí nào ở Section A không? | _ _ _ |
| Có lỡ dùng thời gian tiết kiệm thô thay vì NET không? | _ _ _ |

---

## Insight ban đầu cho Section B + C

Sau khi tính xong, ghi 2-3 nhận xét — đây là điểm để mang vào phần stress test:

Trước khi viết, tự hỏi:

- Phần nào của công thức đang chiếm phần lớn giá trị *(thời gian tiết kiệm hay chất lượng)*?
- Nếu tỷ lệ sử dụng giảm 20%, ROI sẽ rơi xuống bao nhiêu?
- Người mua trong đề bài *(giám đốc / phó tổng)* có chấp nhận ROI ở mức này không?

**Nhận xét 1 — Yếu tố tạo ra phần lớn giá trị**:

```text
(điền vào đây)
```

**Nhận xét 2 — ROI nhạy với yếu tố nào nhất**:

```text
(điền vào đây)
```

**Nhận xét 3 — Người mua có chấp nhận ROI ở mức này không**:

```text
(điền vào đây)
```

---

## Kiểm tra trước khi nộp Section B + C

- [ ] Section B.1 — Vị trí trên ma trận có giải thích 1 câu
- [ ] Section B.2 — Cách định giá có con số cụ thể, đơn vị khách trả tiền rõ
- [ ] Section B.3 — Sản phẩm thật so sánh có tên và cách họ định giá
- [ ] Section B.4 — Mức Usage Anxiety đã đánh giá, có cách giảm nếu cần
- [ ] Section C.1 — NET thời gian tiết kiệm đã trừ đủ 4 phần overhead
- [ ] Section C.2 — Mức lương tính đủ có hệ số (không lấy lương cơ bản trần)
- [ ] Section C.3 — Tỷ lệ sử dụng + chất lượng có lý do giải thích
- [ ] Section C.5 — Giá trị mỗi tháng tính đủ 3 bước
- [ ] Section C.6 — ROI là một số cụ thể *( _ _ _ : 1)*, không "khoảng"
- [ ] Section C.7 — Đã ghi rõ khoảng ROI thuộc nhóm nào
- [ ] Section C.8 — Đã trả lời 4 câu tự kiểm tra

**Đếm số trường đã điền số / giá trị cụ thể**: _ _ _ / 25 trường

Yêu cầu tối thiểu: 22 trường có số / giá trị cụ thể.

---

## Những lỗi hay mắc

| Đừng làm | Nên làm |
|---|---|
| "Tỷ lệ sử dụng 100%" | Thực tế 50-80% giai đoạn thử nghiệm, có lý do |
| "Chất lượng 95%" | Theo benchmark + loại việc trong đề bài |
| Dùng thời gian tiết kiệm thô | NET = Thô − chờ − duyệt − đổi cửa sổ − sửa lại |
| ROI = 30:1 không thắc mắc | Phải xem lại — gần như chắc chắn thổi phồng |
| ROI < 1:1 vẫn đi tiếp | Dừng, xem lại giả định hoặc đổi hướng tiếp cận AI |
| Lương = lương cơ bản trần | Lương tính đủ = cơ bản × 1.3-1.5 *(phụ cấp, văn phòng)* |
| Quên thời gian đổi cửa sổ làm việc | Mỗi lần đổi công cụ là thời gian thật |
| Giá đề xuất < chi phí mỗi đơn vị | Không bền vững — giá phải > chi phí + phần lãi |

---

Sang bước tiếp theo: mở `worksheet/03-stress-test/` để kiểm tra ROI có sống được khi điều kiện xấu đi không. ROI đẹp ở mức trung bình có thể sụp đổ khi tỷ lệ sử dụng / chất lượng / khối lượng lệch. Đó là lúc quyết định cuối *(GO / CONDITIONAL / NO-GO)* được chốt.
