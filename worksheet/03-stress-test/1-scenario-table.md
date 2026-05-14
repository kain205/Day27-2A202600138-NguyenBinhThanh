---
artifact: 1 — Bảng 5 kịch bản stress test
buoc: 3 — Stress Test + Quyết định cuối
phase: Điền 5 kịch bản + ROI mới
thoi-gian: 20 phút
input: 01-cost-model/3-FINAL-cost-model.md + 02-pricing-value/3-FINAL-pricing-value-roi.md + prompts/07-stress-scenario.md
nop-cuoi: Không — file trung gian
---

# 1 — Bảng 5 Kịch bản Stress Test

**Mục tiêu**: tính lại ROI trong **5 kịch bản khác nhau** để xem kinh tế AI có "sống" được khi một giả định trong đề bài bị sai.

Vì sao quan trọng: ROI ở kịch bản gốc (Bước 2) là dự đoán lạc quan — adoption đẹp, quality đẹp, giá nhà cung cấp ổn định. Trong thực tế, ít nhất một trong các giả định đó sẽ trượt. Stress test xem ROI có chịu được khi **một biến** thay đổi, rồi xem điều gì xảy ra khi **hai biến xấu nhất** xảy ra cùng lúc.

**Quy tắc**: mỗi kịch bản chỉ thay đổi **đúng một biến**. Các biến còn lại giữ nguyên từ kịch bản gốc. Nếu đổi cùng lúc nhiều biến, sẽ không biết biến nào đẩy ROI xuống.

---

## Tổng thời gian 20 phút

| Phần | Thời gian | Việc cần làm |
|---|---|---|
| A | 2 phút | Lấy lại các con số gốc từ Mục A + Mục C |
| B | 14 phút | Điền 5 kịch bản (mỗi kịch bản 2-3 phút) |
| C | 4 phút | Tính kịch bản kết hợp 2 cái xấu nhất |

---

## Phần A — Lấy lại các con số gốc

Mở `01-cost-model/3-FINAL-cost-model.md` (Mục A) và `02-pricing-value/3-FINAL-pricing-value-roi.md` (Mục C), kéo các số sau.

| Số liệu | Giá trị |
|---|---|
| Chi phí mỗi tháng (gốc) | $(điền vào đây) |
| Giá trị mỗi tháng (gốc) | $(điền vào đây) |
| ROI (gốc) | (điền vào đây) : 1 |
| Tỷ lệ sử dụng thực tế (gốc) | (điền vào đây) % |
| Hệ số chất lượng (gốc) | (điền vào đây) % |
| Khối lượng mỗi tháng (gốc) | (điền vào đây) việc |
| Chi phí mỗi việc (gốc) | $(điền vào đây) |
| Thời gian thực tiết kiệm mỗi việc | (điền vào đây) phút |

---

## Phần B — 5 kịch bản

Mỗi kịch bản gồm 5 trường cần điền: biến gì thay đổi, chi phí mới, giá trị mới, ROI mới, đánh giá.

**Cách đánh giá ROI mới**:

- *Sống được*: ROI > 3:1
- *Ranh giới*: ROI 1:1 đến 3:1
- *Lỗ*: ROI < 1:1

### Kịch bản 1 — Gốc (mốc tham chiếu)

Đây là kịch bản gốc dùng để so sánh. Không thay đổi gì.

| Trường | Giá trị |
|---|---|
| Biến thay đổi | (không đổi — đây là mốc) |
| Chi phí mỗi tháng | $(điền vào đây — đúng bằng số gốc) |
| Giá trị mỗi tháng | $(điền vào đây — đúng bằng số gốc) |
| **ROI** | (điền vào đây) : 1 |
| Đánh giá | (Sống được / Ranh giới / Lỗ) |

### Kịch bản 2 — Dùng nhiều hơn dự kiến

Người dùng dùng AI **nhiều hơn** ban đầu nghĩ (vd: 20% người dùng "siêu hoạt", chiếm 80% lượng gọi AI).

Trước khi điền, tự hỏi:

- Nếu khối lượng tăng x2 hoặc x3, chi phí API có tăng đúng tỷ lệ không, hay có "bậc thang" (vượt mốc giá doanh nghiệp thì giá đổi)?
- Giá trị cũng tăng theo khối lượng không, hay có giới hạn (vd: chỉ có một số nhất định việc có giá trị)?

| Trường | Giá trị | Lý do |
|---|---|---|
| Biến thay đổi *(Khối lượng × bao nhiêu lần)* | (điền vào đây — vd: × 2, × 3, × 5) | (điền lý do, vd: "20% người dùng siêu hoạt") |
| Khối lượng mới | (điền vào đây) việc | Khối lượng gốc × số nhân |
| Chi phí mới | $(điền vào đây) | Khối lượng tăng → chi phí API + công cụ phụ trợ + người kiểm tăng tỷ lệ |
| Giá trị mới | $(điền vào đây) | Khối lượng tăng → giá trị tăng (cùng tỷ lệ) |
| **ROI** | (điền vào đây) : 1 | Giá trị / Chi phí |
| Đánh giá | (Sống được / Ranh giới / Lỗ) | |

**Điều cần để ý**: kịch bản này xem **chi phí có phình nhanh hơn giá trị không**.

- Trường hợp thật: Replit từng lỗ vì 20% người dùng dùng AI cực nhiều, chi phí vượt doanh thu (2024).
- Nếu chi phí và giá trị cùng tăng tỷ lệ → ROI ở kịch bản 2 sẽ gần bằng ROI gốc. Đó là dấu hiệu kinh tế đơn vị ổn.
- Nếu chi phí có "bậc thang" (vượt mốc doanh nghiệp đổi giá) → ROI sụp đột ngột.

### Kịch bản 3 — Ít người dùng thực tế

Chỉ 30-40% người trong nhóm thử nghiệm thực sự dùng AI thường xuyên. Số còn lại đăng nhập nhưng ít dùng.

Trước khi điền, tự hỏi:

- Tỷ lệ thực tế của nhóm thử nghiệm sẽ là bao nhiêu (nếu UX khó, đào tạo thiếu, hoặc người dùng quen lối làm cũ)?
- Khi ít người dùng, chi phí có giảm theo không? *(Gợi ý: thường không — vì hạ tầng đã setup, các gói công cụ phụ trợ vẫn trả theo tháng.)*

| Trường | Giá trị | Lý do |
|---|---|---|
| Biến thay đổi *(Tỷ lệ sử dụng từ ___% xuống ___%)* | (điền vào đây) | (vd: "UX phức tạp, người dùng cần thời gian quen") |
| Giá trị mới | $(điền vào đây) | Giá trị gốc × (Tỷ lệ mới / Tỷ lệ gốc) |
| Chi phí mỗi tháng | $(điền vào đây) | Phần lớn cố định (công cụ phụ trợ vẫn trả, setup vẫn chia đều) |
| **ROI** | (điền vào đây) : 1 | Giá trị mới / Chi phí |
| Đánh giá | (Sống được / Ranh giới / Lỗ) | |

**Điều cần để ý**: chi phí phần lớn cố định, giá trị giảm trực tiếp theo tỷ lệ dùng thực tế → ROI **rất nhạy** với tỷ lệ sử dụng. Đây thường là kịch bản hurt nhất.

### Kịch bản 4 — Chất lượng AI kém hơn dự kiến

Đầu ra AI có chất lượng chỉ 50-60% thay vì 80% như dự đoán. Có thể do: cơ sở tri thức cũ, mô hình thiếu hiểu biết ngành, hoặc gặp nhiều trường hợp khó nhằn.

Trước khi điền, tự hỏi:

- Nếu chất lượng giảm, người kiểm sẽ tốn thêm bao nhiêu thời gian sửa? Chi phí sửa lại có làm chi phí tổng tăng không?
- Khi sản phẩm sai, người dùng có còn dùng tiếp không? Có ảnh hưởng đến tỷ lệ sử dụng không?

| Trường | Giá trị | Lý do |
|---|---|---|
| Biến thay đổi *(Chất lượng từ ___% xuống ___%)* | (điền vào đây) | (vd: "Cơ sở tri thức ngành cũ 30%, mô hình thiếu ngành") |
| Chi phí sửa lại thêm | + $(điền vào đây) /tháng | Thời gian người kiểm sửa các đầu ra sai |
| Giá trị mới | $(điền vào đây) | Giá trị gốc × Tỷ lệ sử dụng × Chất lượng mới − Chi phí sửa lại |
| Chi phí mới | $(điền vào đây) | Có thể tăng nhẹ vì chạy lại / sinh lại |
| **ROI** | (điền vào đây) : 1 | |
| Đánh giá | (Sống được / Ranh giới / Lỗ) | |

### Kịch bản 5 — Nhà cung cấp đổi luật

Nhà cung cấp tăng giá ×2, hoặc dừng hỗ trợ mô hình hiện tại buộc nhóm chuyển sang mô hình đắt hơn.

Trước khi điền, tự hỏi:

- Nếu giá API ×2, có thể chuyển sang nhà cung cấp khác để giữ giá không? Mất bao lâu để chuyển?
- Có hợp đồng khoá giá nào với nhà cung cấp không, hay đang dùng giá lẻ?

| Trường | Giá trị | Lý do |
|---|---|---|
| Biến thay đổi *(Chi phí API × bao nhiêu lần)* | (điền vào đây — vd: × 2, × 3) | (vd: "Nhà cung cấp tăng giá / mô hình bị dừng hỗ trợ") |
| Chi phí API mới mỗi tháng | $(điền vào đây) | Chi phí API gốc × số nhân |
| Chi phí mới mỗi tháng | $(điền vào đây) | API mới + công cụ phụ trợ + người kiểm + setup |
| Giá trị mỗi tháng | $(điền vào đây — bằng số gốc) | Không đổi |
| **ROI** | (điền vào đây) : 1 | |
| Đánh giá | (Sống được / Ranh giới / Lỗ) | |

**Tham khảo thực tế**:

- Salesforce đổi giá AI **3 lần** trong 18 tháng (2024).
- OpenAI đã **giảm giá 280×** trong 2 năm (tin tốt — nhưng đừng dựa vào xu hướng giảm sẽ tiếp diễn).
- Anthropic dừng hỗ trợ Claude 3.5 buộc khách chuyển lên Claude 3.7 hoặc 4 (giá khác).

---

## Phần C — Kịch bản kết hợp xấu nhất

Trong thực tế, không bao giờ chỉ **một** giả định trượt — thường là vài cái trượt cùng lúc. Phần này áp dụng **2 kịch bản xấu nhất đồng thời** để xem ROI có còn sống không.

### C.1 — Chọn 2 kịch bản xấu nhất

Nhìn lại 4 kịch bản (2 đến 5), điền 2 cái có ROI thấp nhất.

- **Kịch bản xấu nhất 1**: (điền tên + ROI, vd: "Ít người dùng, ROI = 0.9:1")

```text
(điền vào đây)
```

- **Kịch bản xấu nhất 2**: (điền tên + ROI)

```text
(điền vào đây)
```

### C.2 — Tính kết hợp

Áp dụng 2 thay đổi đồng thời. Chi phí và giá trị mới là kết quả khi cả hai biến đều xấu.

| Trường | Giá trị | Công thức |
|---|---|---|
| Thay đổi 1 | (điền vào đây) | (vd: Tỷ lệ sử dụng từ 70% xuống 30%) |
| Thay đổi 2 | (điền vào đây) | (vd: Chi phí API × 2) |
| Chi phí kết hợp | $(điền vào đây) | Áp cả 2 thay đổi lên chi phí |
| Giá trị kết hợp | $(điền vào đây) | Áp cả 2 thay đổi lên giá trị |
| **ROI kết hợp** | (điền vào đây) : 1 | Giá trị / Chi phí |

### C.3 — Đọc kết quả

Đối chiếu ROI kết hợp với bảng dưới để biết kết luận thiên về phía nào.

| ROI kết hợp | Diễn giải | Quyết định thiên về |
|---|---|---|
| > 3:1 | Vững — sống tốt cả khi 2 biến xấu cùng lúc | GO |
| 1.5 – 3:1 | Sống được nhưng biên mỏng | GO |
| 1 – 1.5:1 | Điểm hòa vốn — cần kế hoạch giảm rủi ro | CONDITIONAL |
| 0.5 – 1:1 | Lỗ — cần thiết kế lại hoặc thu hẹp phạm vi | NO-GO |
| < 0.5:1 | Nguy hiểm — không bền — xem lại có nên triển khai | NO-GO |

**ROI kết hợp của nhóm**:

```text
(điền vào đây) : 1
```

**Diễn giải 1-2 câu cho nhóm** *(không chỉ copy bảng — viết câu cụ thể với số của nhóm)*:

```text
(điền vào đây)
```

---

## Phần D — Điểm hòa vốn (khuyến nghị, không bắt buộc)

Tính ngưỡng nào của tỷ lệ sử dụng hoặc chất lượng mà ROI = 1:1 (hòa vốn). Sau khi tính, nhóm biết chính xác "khi nào thì pilot fail".

### D.1 — Điểm hòa vốn của tỷ lệ sử dụng

Giữ chất lượng = gốc, hỏi: **tỷ lệ sử dụng bao nhiêu thì ROI = 1:1?**

Công thức:

```text
Chi phí (cố định) = Giá trị gốc × X% × Hệ số chất lượng
→ X% = Chi phí / (Giá trị gốc × Hệ số chất lượng)
```

Tính cho nhóm:

```text
X% = $(điền vào đây) / ($(điền vào đây) × (điền vào đây)%) = (điền vào đây) %
```

**Điểm hòa vốn của tỷ lệ sử dụng**: (điền vào đây) %

Diễn giải 1 câu *(vd: "Nếu tỷ lệ sử dụng dưới ___ %, ROI < 1:1 → pilot fail")*:

```text
(điền vào đây)
```

### D.2 — Điểm hòa vốn của chất lượng

Giữ tỷ lệ sử dụng = gốc, hỏi: **chất lượng bao nhiêu thì ROI = 1:1?**

Công thức:

```text
Chi phí = Giá trị gốc × Tỷ lệ sử dụng × Y%
→ Y% = Chi phí / (Giá trị gốc × Tỷ lệ sử dụng)
```

Tính cho nhóm:

```text
Y% = $(điền vào đây) / ($(điền vào đây) × (điền vào đây)%) = (điền vào đây) %
```

**Điểm hòa vốn của chất lượng**: (điền vào đây) %

---

## Phần E — Kiểm tra trước khi chuyển sang `2-verdict-draft.md`

- [ ] Đủ 5 kịch bản, mỗi cái có chi phí + giá trị + ROI cụ thể.
- [ ] Mỗi kịch bản chỉ thay đổi đúng một biến.
- [ ] Kịch bản 2 (dùng nhiều) có lý do cụ thể *(vd: "20% người siêu hoạt chiếm 80% gọi")*.
- [ ] Kịch bản 3 (ít người dùng) có tỷ lệ thực sự thấp hơn gốc *(vd: 30% nếu gốc = 70%)*.
- [ ] Kịch bản 4 (chất lượng kém) thấp rõ rệt *(vd: 50% nếu gốc = 80%, không phải 75%)*.
- [ ] Kịch bản 5 (nhà cung cấp đổi luật) có tham khảo thực tế *(vd: Anthropic dừng Claude 3.5)*.
- [ ] Kịch bản kết hợp dùng đúng **2 kịch bản xấu nhất đồng thời**, không phải "tất cả tệ".
- [ ] Đã đọc ROI kết hợp theo bảng và viết 1-2 câu diễn giải.
- [ ] (Khuyến nghị) Có tính điểm hòa vốn của tỷ lệ sử dụng và chất lượng.

---

## Những lỗi hay mắc

| Đừng | Thay vào đó |
|---|---|
| "Đề bài tôi không có rủi ro dùng nhiều" | Mọi đề bài đều có — ít nhất là phạm vi bị mở rộng |
| Tỷ lệ sử dụng xấu = 50% (gần bằng gốc 60%) | Phải xấu rõ — vd: 30% nếu gốc = 70% |
| Chất lượng xấu = 80% (gần bằng gốc 85%) | Phải xấu rõ — vd: 50%, không phải tinh chỉnh nhẹ |
| Nhà cung cấp đổi luật = giá × 1.1 | Thực tế là × 2 đến × 3, hoặc dừng hỗ trợ hẳn |
| Kết hợp = chỉ kịch bản 5 nặng hơn | Kết hợp = 2 kịch bản xảy ra **đồng thời** |
| Quên chi phí sửa lại ở kịch bản chất lượng | Khi chất lượng kém, người kiểm phải sửa nhiều → chi phí thật tăng |
| Bỏ điểm hòa vốn | Khuyến nghị làm — biết "ngưỡng sống chết" có ích cho phần quyết định |

---

## Câu hỏi dẫn sang `2-verdict-draft.md`

Sau khi điền xong, chuẩn bị 1-2 câu trả lời cho mỗi câu hỏi sau:

- Kịch bản nào hurt nhất? Vì sao?
- ROI kết hợp có > 1:1 không? Nếu không, nhóm sẽ thay đổi gì?
- Điểm hòa vốn của tỷ lệ sử dụng có thực tế không *(nhóm có tin đạt được không)*?

```text
1. (điền vào đây)
2. (điền vào đây)
3. (điền vào đây)
```

Chuyển sang `2-verdict-draft.md` để viết bản nháp quyết định.
