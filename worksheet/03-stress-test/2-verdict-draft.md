---
artifact: 2 — Bản nháp quyết định cuối
buoc: 3 — Stress Test + Quyết định cuối
phase: Viết quyết định cuối + điều kiện kèm theo
thoi-gian: 10 phút
input: 1-scenario-table.md + prompts/08-verdict-writing.md
nop-cuoi: Không — file trung gian
---

# 2 — Bản nháp Quyết định Cuối

**Mục tiêu**: dựa trên 5 kịch bản + ROI kết hợp + điểm hòa vốn ở file trước, **viết một quyết định cuối**: GO / CONDITIONAL / NO-GO. Bản nháp này sẽ được gọt lại và dán vào Mục D ở file FINAL.

Vì sao quan trọng: phân tích tốn 1 giờ — quyết định chỉ tốn 3 câu. Nhưng quyết định **không có lý do cụ thể** sẽ bị người mua từ chối ngay. Bản nháp này tập cho nhóm viết quyết định **đứng được trước câu hỏi của người mua**.

**Quy tắc**:

- GO / CONDITIONAL / NO-GO phải có **lý do cụ thể bằng số**, không chỉ "cảm thấy ổn".
- CONDITIONAL phải có **3-5 điều kiện cụ thể** + chỉ số theo dõi + ngưỡng dừng.
- NO-GO phải nói rõ **cần thay đổi gì** để khả thi — không từ chối khô khan.

---

## Tổng thời gian 10 phút

| Phần | Thời gian | Việc cần làm |
|---|---|---|
| A | 3 phút | Áp 3 tiêu chí → chọn một trong ba quyết định |
| B | 4 phút | Viết bản nháp + điều kiện / thay đổi |
| C | 3 phút | Cặp tự thách thức quyết định của mình |

---

## Phần A — Khung 3 tiêu chí quyết định

### A.1 — Bảng tiêu chí

| Tiêu chí | GO | CONDITIONAL | NO-GO |
|---|---|---|---|
| ROI gốc | > 3:1 | 1.5 – 3:1 | < 1.5:1 |
| Số kịch bản (trong 4 kịch bản 2-5) ở trạng thái "Sống được" | 3-4 | 1-2 | 0 |
| ROI kết hợp xấu nhất | > 1.5:1 | 1 – 1.5:1 | < 1:1 |

### A.2 — Áp dụng cho nhóm

Lấy 3 con số trên từ `1-scenario-table.md` và điền vào bảng dưới.

| Tiêu chí | Giá trị của nhóm | Tiêu chí này nghiêng về |
|---|---|---|
| ROI gốc | (điền vào đây) : 1 | (GO / CONDITIONAL / NO-GO) |
| Số kịch bản "Sống được" trong 4 kịch bản 2-5 | (điền vào đây) / 4 | (GO / CONDITIONAL / NO-GO) |
| ROI kết hợp xấu nhất | (điền vào đây) : 1 | (GO / CONDITIONAL / NO-GO) |

**Quyết định tổng hợp dự kiến**:

```text
(điền vào đây — GO / CONDITIONAL / NO-GO)
```

**Cách đọc kết quả**:

- Nếu 3 hàng cùng nghiêng về một quyết định → quyết định rõ ràng.
- Nếu lệch *(vd: ROI gốc nghiêng GO nhưng ROI kết hợp nghiêng NO-GO)* → thường an toàn nhất là **CONDITIONAL** với điều kiện chặt.

---

## Phần B — Viết bản nháp quyết định

Phần này có 3 mẫu — chọn mẫu khớp với quyết định đã chọn ở Phần A. **Đọc mẫu rồi viết bằng số của nhóm**, không copy mẫu nguyên xi.

### B.1 — Nếu GO

Trước khi viết, tự hỏi:

- Tại sao mình tin GO mà không phải CONDITIONAL? Có dữ liệu cứng nào về tỷ lệ sử dụng / chất lượng không?
- ROI kết hợp xấu nhất có thực sự > 1.5:1 không? Có chắc không phải lạc quan?

**Khung gợi ý**:

```text
Triển khai pilot như phạm vi đã chốt. Đề bài #(số) — (tên ngắn). Phạm vi:
(số người thử) người trong (số ngày) ngày, ngân sách $(số) /tháng.

ROI ở kịch bản gốc là (số) : 1. Sống được trong (số) / 4 kịch bản xấu.
Kịch bản kết hợp 2 cái xấu nhất ((tên 2 kịch bản)) cho ROI (số) : 1,
vẫn trên ngưỡng 1.5 : 1.
```

**Bản nháp của nhóm** *(viết bằng số của nhóm, không copy mẫu)*:

```text
(điền vào đây)
```

### B.2 — Nếu CONDITIONAL (trường hợp phổ biến nhất)

Trước khi viết, tự hỏi:

- Điều kiện nào là điều kiện sống chết *(nếu không đạt thì coi như fail)*?
- Mỗi điều kiện đo bằng gì *(không phải "cảm thấy ổn", mà là một con số đo được hàng tuần)*?
- Khi nào dừng pilot và xem xét lại *(số cụ thể + thời gian cụ thể)*?

**Khung gợi ý**:

```text
CONDITIONAL GO. Đề bài #(số) — (tên). Triển khai pilot **với các điều kiện**:

- Điều kiện 1: (vd: Tỷ lệ sử dụng phải đạt ≥ X% trong tháng 1, không thì dừng xem xét lại)
- Điều kiện 2: (vd: Khoá giá API với nhà cung cấp 6 tháng, hoặc setup mô hình dự phòng)
- Điều kiện 3: (vd: Cổng chi phí hàng tháng $X — không vượt ngân sách thử nghiệm)
- Điều kiện 4: (vd: Hệ số chất lượng đo bằng lấy mẫu ngẫu nhiên 50 việc/tuần, mục tiêu ≥ Y%)

Theo dõi hàng tuần: tỷ lệ sử dụng, chi phí mỗi việc, hệ số chất lượng.

Ngưỡng dừng pilot: nếu trong 30 ngày liên tiếp tỷ lệ sử dụng < X% HOẶC chất lượng < Y%
HOẶC chi phí mỗi việc > $Z → dừng pilot và xem xét lại.
```

**Bản nháp của nhóm**:

```text
(điền vào đây)
```

### B.3 — Nếu NO-GO

Trước khi viết, tự hỏi:

- NO-GO là "không bao giờ" hay "không phải lúc này"? Khác nhau quan trọng.
- Cần thay đổi cái gì cụ thể thì có thể quay lại quyết định *(đổi mô hình rẻ hơn / mở rộng phạm vi / nới ràng buộc kiểm tra)*?

**Khung gợi ý**:

```text
NO-GO theo phạm vi hiện tại. Đề bài #(số) — (tên).

Lý do: ROI gốc (số) : 1 < 1.5, hoặc ROI kết hợp xấu nhất (số) : 1 < 1.

Cần thay đổi để khả thi:

- Thay đổi 1: (vd: Đổi mô hình — dùng GPT-4o-mini cho việc đơn giản
  thay vì Claude 3.5 Sonnet → chi phí mỗi việc giảm 80%)
- Thay đổi 2: (vd: Mở rộng phạm vi pilot từ 5 lên 15 người → setup chia đều tốt hơn)
- Thay đổi 3: (vd: Nới ràng buộc 100% người kiểm cho các việc đơn giản → giảm chi phí người kiểm)

Loại NO-GO: (Không phải lúc này — có thể quay lại khi A, B / Không bao giờ — về bản chất không phù hợp).
```

**Bản nháp của nhóm**:

```text
(điền vào đây)
```

---

## Phần C — Cặp tự thách thức quyết định

Trước khi đem quyết định sang file FINAL, cặp tự đặt 3 câu hỏi sau cho nhau. Đây là phần quan trọng nhất — vì người mua thật **sẽ hỏi đúng những câu này**.

### C.1 — Câu hỏi 1: Tại sao không CONDITIONAL nếu đang chọn GO?

Hầu hết pilot AI thực tế nên đi CONDITIONAL. Nếu nhóm chọn GO, kiểm tra lại:

- Có dữ liệu cứng nào hỗ trợ tỷ lệ sử dụng > 80%? *(không phải dự đoán — dữ liệu)*
- Có dữ liệu cứng nào hỗ trợ chất lượng > 85%?
- ROI kết hợp xấu nhất thực sự > 1.5:1, hay nhóm đang lạc quan ở chỗ nào?

Trả lời của nhóm *(nếu chọn GO)*:

```text
(điền vào đây)
```

### C.2 — Câu hỏi 2: Tại sao không NO-GO nếu đang chọn CONDITIONAL?

Một CONDITIONAL **với điều kiện không khả thi** thực ra là NO-GO trá hình:

- Điều kiện 1 có khả thi để đạt trong thời gian thử nghiệm không?
- Nếu cần tỷ lệ sử dụng > 80% mới sống mà điều đó khó đạt → thực ra là NO-GO.
- Nếu cần chi phí giảm 50% mới sống mà khó đàm phán → thực ra là NO-GO.

Thành thật hơn là nói NO-GO ngay từ đầu, có lý do để quay lại sau.

Trả lời của nhóm *(nếu chọn CONDITIONAL)*:

```text
(điền vào đây)
```

### C.3 — Câu hỏi 3: Người mua (CTO / VP) sẽ phản ứng thế nào?

Đặt mình vào vai người mua trong trường 6 của đề bài. Đọc bản nháp quyết định một lần nữa qua mắt họ.

- Họ thấy GO chắc chắn nhưng không có stress test → có tin được không?
- Họ thấy CONDITIONAL với 3 điều kiện rõ ràng → có hành động được không?
- Họ thấy NO-GO với lý do rõ ràng → có giúp tiết kiệm chi phí không?

Kinh nghiệm thực tế: người mua tốt **thích CONDITIONAL với điều kiện rõ** hơn **GO chắc chắn không stress test** — vì CONDITIONAL chứng tỏ nhóm đã suy nghĩ kỹ.

Quyết định cuối của nhóm sau khi tự thách thức:

```text
(điền vào đây — GO / CONDITIONAL / NO-GO + 1 câu lý do)
```

---

## Phần D — Bản nháp chi tiết (chuẩn bị dán sang FINAL)

### D.1 — Quyết định chọn

```text
(điền vào đây — GO / CONDITIONAL / NO-GO)
```

### D.2 — Phát biểu quyết định 3-4 câu

Đây là phần sẽ dán nguyên vào Mục D.4 của file FINAL.

```text
(điền câu 1 — quyết định gì + đề bài nào)
```

```text
(điền câu 2 — lý do bằng số: ROI gốc, số kịch bản sống, ROI kết hợp)
```

```text
(điền câu 3 — điều kiện sống chết hoặc thay đổi cần thiết)
```

```text
(điền câu 4 — phạm vi & thời gian: pilot bao nhiêu người, bao nhiêu tháng, ngân sách bao nhiêu)
```

### D.3 — Điều kiện cụ thể (nếu CONDITIONAL)

Mỗi điều kiện cần: nội dung cụ thể, đo bằng gì, lúc nào, hành động nếu không đạt. Ít nhất 3, tối đa 5.

1. **Điều kiện 1**:

```text
(điền vào đây — vd: "Tỷ lệ sử dụng ≥ 60% trong tháng 1, đo bằng tỷ lệ người hoạt động /
tổng người thử, kiểm cuối tháng 1, nếu không đạt → dừng và xem xét lại")
```

2. **Điều kiện 2**:

```text
(điền vào đây)
```

3. **Điều kiện 3**:

```text
(điền vào đây)
```

4. **Điều kiện 4** *(nếu cần)*:

```text
(điền vào đây)
```

5. **Điều kiện 5** *(nếu cần)*:

```text
(điền vào đây)
```

### D.4 — Chỉ số theo dõi hàng tuần / hàng tháng

3-5 chỉ số nhóm sẽ theo dõi trong suốt pilot. Mỗi chỉ số: tên, đo bằng nguồn nào, ngưỡng chấp nhận.

- **Chỉ số 1**:

```text
(điền vào đây — vd: "Tỷ lệ sử dụng = người hoạt động / tổng người thử, lấy từ log dùng, hàng tuần, ngưỡng ≥ 60%")
```

- **Chỉ số 2**:

```text
(điền vào đây)
```

- **Chỉ số 3**:

```text
(điền vào đây)
```

- **Chỉ số 4** *(nếu cần)*:

```text
(điền vào đây)
```

- **Chỉ số 5** *(nếu cần)*:

```text
(điền vào đây)
```

### D.5 — Ngưỡng dừng pilot

Trigger cụ thể bằng số + thời gian + hành động. Tránh "nếu pilot thất bại" — quá mơ hồ.

- **Trigger 1**:

```text
(điền vào đây — vd: "Tỷ lệ sử dụng < 40% trong 30 ngày liên tiếp → dừng và xem xét lại")
```

- **Trigger 2**:

```text
(điền vào đây)
```

### D.6 — Thay đổi cần thiết (nếu NO-GO)

Liệt kê 2-3 thay đổi để nhóm có thể quay lại quyết định. Mỗi thay đổi cần kèm tác động dự kiến lên ROI.

1. **Thay đổi 1**:

```text
(điền vào đây — vd: "Đổi từ Claude 3.5 Sonnet sang GPT-4o-mini cho việc đơn giản → chi phí mỗi việc giảm 80%, ROI tăng từ 0.8:1 lên 2.1:1")
```

2. **Thay đổi 2**:

```text
(điền vào đây)
```

3. **Thay đổi 3**:

```text
(điền vào đây)
```

---

## Phần E — Bảng kiểm trước khi chuyển sang `3-FINAL-stress-test-verdict.md`

- [ ] Đã chọn rõ 1 trong 3 quyết định (GO / CONDITIONAL / NO-GO).
- [ ] Phát biểu quyết định 3-4 câu sẵn sàng để dán vào FINAL.
- [ ] Nếu CONDITIONAL: có 3-5 điều kiện cụ thể, đo được, có thời gian.
- [ ] Có 3-5 chỉ số theo dõi với ngưỡng chấp nhận.
- [ ] Có ngưỡng dừng pilot cụ thể *(số + thời gian + hành động)*.
- [ ] Đã trả lời câu hỏi tự thách thức ở Phần C.
- [ ] Đã đặt mình vào vai người mua để đọc lại bản nháp.

---

## Những lỗi hay mắc

| Đừng | Thay vào đó |
|---|---|
| "Có vẻ ổn" | Cụ thể GO / CONDITIONAL / NO-GO với lý do bằng số |
| GO chắc chắn không có stress test | CONDITIONAL với điều kiện rõ — đứng được trước người mua hơn |
| CONDITIONAL nhưng không có điều kiện cụ thể | 3-5 điều kiện đo được + thời gian |
| CONDITIONAL với điều kiện không khả thi | Thành thật nói NO-GO |
| NO-GO mà không nói cần đổi gì | Liệt kê 2-3 thay đổi để khả thi |
| Quên góc nhìn người mua | Đọc lại một lần qua mắt CTO / VP — có đứng được không? |

---

## Sau khi xong bản nháp

Chuyển sang `3-FINAL-stress-test-verdict.md` để gộp Mục D hoàn chỉnh: bảng 5 kịch bản + kịch bản kết hợp + quyết định + điều kiện + theo dõi + ngưỡng dừng.
