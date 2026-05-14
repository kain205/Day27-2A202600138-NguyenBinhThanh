---
artifact: 3 — Chốt Stress Test + Quyết định cuối (Mục D của bảng kinh tế)
buoc: 3 — Stress Test + Quyết định cuối
phase: Chốt mục D
thoi-gian: 10 phút
input: 1-scenario-table.md + 2-verdict-draft.md
nop-cuoi: Có — mục D sẽ được dán vào `04-FINAL-economics-sheet.md` để nộp
---

# 3 — Chốt Stress Test + Quyết định cuối (Mục D)

**Mục tiêu**: gộp 5 kịch bản từ `1-scenario-table.md` + bản nháp quyết định từ `2-verdict-draft.md` thành **Mục D — Stress Test + Quyết định cuối** đầy đủ.

Đây là file cuối của Bước 3 trong Lab. Mục D này sẽ được dán vào `04-FINAL-economics-sheet.md`.

Vì sao Mục D quan trọng: đây là phần **người mua (CTO / VP / lead) đọc kỹ nhất**. Mục A, B, C cho thấy nhóm biết tính. Mục D cho thấy nhóm biết **quyết định** — và bảo vệ quyết định bằng số chứ không bằng cảm tính.

**Quy tắc khi điền**:

- Bảng 5 kịch bản phải có chi phí / giá trị / ROI mới cho từng cái.
- Quyết định phải có điều kiện hoặc thay đổi cụ thể với thời gian.
- Mỗi chỉ số theo dõi phải kèm ngưỡng chấp nhận (con số cụ thể).

---

## Tổng thời gian 10 phút

| Phần | Thời gian | Việc cần làm |
|---|---|---|
| D.0 | 1 phút | Điền thông tin nhóm |
| D.1 → D.3 | 4 phút | Dán bảng 5 kịch bản + kịch bản kết hợp + điểm hòa vốn |
| D.4 → D.5 | 3 phút | Quyết định + điều kiện (hoặc thay đổi nếu NO-GO) |
| D.6 → D.8 | 2 phút | Chỉ số theo dõi + ngưỡng dừng + insight ban đầu |

---

## Thông tin nhóm

- **Số đề bài + tên ngắn**:

```text
(điền vào đây)
```

- **Tên + mã học viên × 2 thành viên cặp**:

```text
(điền vào đây)
```

- **Ngày tính** *(YYYY-MM-DD)*:

```text
(điền vào đây)
```

- **Phiên bản**:

```text
(điền vào đây)
```

---

## Mục D — Stress Test + Quyết định cuối

### D.1 — Bảng 5 kịch bản

Lấy từ `1-scenario-table.md` phần B. Mỗi dòng phải có 4 con số: chi phí, giá trị, ROI, đánh giá.

| # | Kịch bản | Biến thay đổi | Chi phí ($/tháng) | Giá trị ($/tháng) | ROI | Đánh giá |
|---|---|---|---|---|---|---|
| 1 | Gốc | (không đổi — mốc tham chiếu) | $(điền vào đây) | $(điền vào đây) | (điền vào đây):1 | (Sống được / Ranh giới / Lỗ) |
| 2 | Dùng nhiều | Khối lượng × (điền vào đây) | $(điền vào đây) | $(điền vào đây) | (điền vào đây):1 | (Sống được / Ranh giới / Lỗ) |
| 3 | Ít người dùng | Tỷ lệ sử dụng từ ___% xuống ___% | $(điền vào đây) | $(điền vào đây) | (điền vào đây):1 | (Sống được / Ranh giới / Lỗ) |
| 4 | Chất lượng kém | Chất lượng từ ___% xuống ___% | $(điền vào đây) | $(điền vào đây) | (điền vào đây):1 | (Sống được / Ranh giới / Lỗ) |
| 5 | Nhà cung cấp đổi luật | Chi phí API × (điền vào đây) | $(điền vào đây) | $(điền vào đây) | (điền vào đây):1 | (Sống được / Ranh giới / Lỗ) |

### D.2 — Kịch bản kết hợp xấu nhất

Lấy từ `1-scenario-table.md` phần C.

| Trường | Giá trị |
|---|---|
| Kịch bản xấu nhất 1 | # (số) — (tên) — ROI (số):1 |
| Kịch bản xấu nhất 2 | # (số) — (tên) — ROI (số):1 |
| Mô tả thay đổi kết hợp | (điền vào đây — vd: "Tỷ lệ sử dụng từ 70% xuống 30% + chi phí API × 2") |
| Chi phí kết hợp | $(điền vào đây) /tháng |
| Giá trị kết hợp | $(điền vào đây) /tháng |
| **ROI kết hợp** | (điền vào đây):1 |
| Mức độ vững | (Vững > 3:1 / Sống được 1.5-3:1 / Hòa vốn 1-1.5:1 / Lỗ 0.5-1:1 / Nguy hiểm < 0.5:1) |

### D.3 — Điểm hòa vốn (khuyến nghị)

Lấy từ `1-scenario-table.md` phần D. Phần này không bắt buộc nhưng làm sẽ rõ hơn cho người mua.

| Trường | Giá trị |
|---|---|
| Điểm hòa vốn của tỷ lệ sử dụng *(tại chất lượng = gốc)* | (điền vào đây) % |
| Điểm hòa vốn của chất lượng *(tại tỷ lệ sử dụng = gốc)* | (điền vào đây) % |
| Diễn giải 1 câu | (vd: "Pilot fail nếu tỷ lệ sử dụng < (số)% HOẶC chất lượng < (số)%") |

### D.4 — Quyết định cuối

Dán từ `2-verdict-draft.md` phần D.1 và D.2.

**Quyết định**: (chọn 1) GO / CONDITIONAL / NO-GO

```text
(điền vào đây — GO, CONDITIONAL, hay NO-GO)
```

**Phát biểu quyết định 3-4 câu** *(dán nguyên từ bản nháp)*:

```text
(điền câu 1)
```

```text
(điền câu 2)
```

```text
(điền câu 3)
```

```text
(điền câu 4)
```

### D.5 — Điều kiện cụ thể (nếu CONDITIONAL)

Dán từ `2-verdict-draft.md` phần D.3. Mỗi dòng có 5 cột: nội dung, đo bằng gì, thời điểm kiểm, ngưỡng, hành động nếu không đạt.

| # | Điều kiện | Đo bằng gì | Thời điểm kiểm | Ngưỡng | Hành động nếu không đạt |
|---|---|---|---|---|---|
| 1 | (điền vào đây) | (điền vào đây) | (điền vào đây) | (điền vào đây) | (điền vào đây) |
| 2 | (điền vào đây) | (điền vào đây) | (điền vào đây) | (điền vào đây) | (điền vào đây) |
| 3 | (điền vào đây) | (điền vào đây) | (điền vào đây) | (điền vào đây) | (điền vào đây) |
| 4 | (điền nếu cần) | (điền vào đây) | (điền vào đây) | (điền vào đây) | (điền vào đây) |
| 5 | (điền nếu cần) | (điền vào đây) | (điền vào đây) | (điền vào đây) | (điền vào đây) |

### D.6 — Chỉ số theo dõi hàng tuần / hàng tháng

Dán từ `2-verdict-draft.md` phần D.4. 3-5 chỉ số cần theo dõi liên tục trong pilot.

| Chỉ số | Tần suất kiểm | Nguồn dữ liệu | Ngưỡng chấp nhận |
|---|---|---|---|
| Tỷ lệ sử dụng | (Tuần / Tháng) | (điền vào đây — vd: log dùng) | ≥ (điền vào đây) % |
| Chi phí mỗi việc | (Tuần / Tháng) | (điền vào đây — vd: log thanh toán) | ≤ $(điền vào đây) |
| Hệ số chất lượng | (Tuần / Tháng) | (điền vào đây — vd: lấy mẫu 50 việc/tuần) | ≥ (điền vào đây) % |
| Mức hài lòng người dùng | (Tuần / Tháng) | (điền vào đây — vd: khảo sát NPS) | NPS ≥ (điền vào đây) |
| Tổng chi phí mỗi tháng | (Tuần / Tháng) | (điền vào đây — vd: phòng tài chính) | ≤ $(điền vào đây) |

### D.7 — Ngưỡng dừng pilot

Dán từ `2-verdict-draft.md` phần D.5. Mỗi trigger gồm: chỉ số nào, ngưỡng nào, trong bao lâu, hành động gì.

- **Trigger 1**:

```text
(điền vào đây — vd: "Tỷ lệ sử dụng < 40% trong 30 ngày liên tiếp → dừng pilot và xem xét lại")
```

- **Trigger 2**:

```text
(điền vào đây — vd: "Chi phí mỗi việc > $0.20 trong 2 tuần liên tiếp")
```

- **Trigger 3**:

```text
(điền vào đây — vd: "Chất lượng < 50% trong 30 ngày")
```

- **Trigger 4** *(nếu cần)*:

```text
(điền vào đây — vd: "Sự cố an ninh / tuân thủ nghiêm trọng → dừng ngay lập tức")
```

### D.8 — Thay đổi cần thiết (nếu NO-GO)

Dán từ `2-verdict-draft.md` phần D.6. Mỗi thay đổi kèm tác động dự kiến lên ROI.

| # | Thay đổi | Tác động ROI dự kiến |
|---|---|---|
| 1 | (điền vào đây) | (điền vào đây — vd: "Chi phí giảm 80%, ROI tăng từ 0.8:1 lên 2.1:1") |
| 2 | (điền vào đây) | (điền vào đây) |
| 3 | (điền vào đây) | (điền vào đây) |

**Loại NO-GO**: chọn 1

- ( ) "Không phải lúc này" — có thể quay lại khi nào *(điền điều kiện)*:

```text
(điền vào đây)
```

- ( ) "Không bao giờ" — về bản chất không phù hợp. Lý do:

```text
(điền vào đây)
```

---

## 2-3 điểm đáng chú ý từ Mục D

Sau khi điền xong, nhóm tự rút ra 2-3 điểm đáng chú ý. Đây là phần ý nghĩa nhất — không phải con số, mà là **hiểu cái gì sẽ làm pilot này thắng hay thua**.

Trước khi viết, tự hỏi:

- Kịch bản nào hurt nhất? Vì sao? *(thường là kịch bản ít người dùng — chi phí cố định, giá trị giảm trực tiếp)*
- Khi 2 biến cùng xấu, ROI sụp nhanh hơn hay chậm hơn so với từng cái riêng lẻ?
- Một câu lời khuyên cho người mua đọc Mục D này — họ cần để ý đến biến gì nhất?

→ Viết 2-3 điểm:

```text
1. Kịch bản hurt nhất: (điền vào đây)
2. Pattern khi kết hợp 2 biến xấu: (điền vào đây)
3. Lời khuyên cho người mua: (điền vào đây)
```

---

## Bảng kiểm trước khi gộp vào file FINAL

- [ ] D.1 — Bảng 5 kịch bản đủ chi phí + giá trị + ROI + đánh giá.
- [ ] D.2 — Kịch bản kết hợp dùng **đúng 2 kịch bản xấu nhất**, không phải "tất cả tệ".
- [ ] D.3 — Điểm hòa vốn của tỷ lệ sử dụng + chất lượng *(khuyến nghị nhưng cộng điểm)*.
- [ ] D.4 — Đã chọn rõ 1 quyết định, có phát biểu 3-4 câu.
- [ ] D.5 — Nếu CONDITIONAL: 3-5 điều kiện có nội dung + cách đo + thời điểm + ngưỡng + hành động.
- [ ] D.6 — 3-5 chỉ số theo dõi với ngưỡng cụ thể.
- [ ] D.7 — Ngưỡng dừng pilot cụ thể *(số + thời gian + hành động)*.
- [ ] D.8 — Nếu NO-GO: 2-3 thay đổi với tác động ROI dự kiến.
- [ ] Có 2-3 điểm đáng chú ý.

Số trường đã điền có số / quyết định cụ thể: ___ / 35+ trường (yêu cầu tối thiểu 28).

---

## Những lỗi hay mắc (kiểm tra lần cuối)

| Đừng | Thay vào đó |
|---|---|
| ROI giống nhau ở cả 5 kịch bản | Ít nhất 1-2 kịch bản phải hurt rõ rệt |
| Kịch bản kết hợp = kịch bản 5 nặng hơn | Kịch bản kết hợp = 2 kịch bản xảy ra đồng thời |
| Quyết định không có điều kiện | CONDITIONAL bắt buộc 3-5 điều kiện |
| Điều kiện = "sẽ theo dõi tỷ lệ sử dụng" | Điều kiện = "Tỷ lệ sử dụng ≥ 60% trong tháng 1" *(có số + thời gian)* |
| Ngưỡng dừng = "nếu pilot thất bại" | Ngưỡng dừng = "Tỷ lệ sử dụng < 40% trong 30 ngày" |
| NO-GO không nói thay đổi gì | NO-GO bắt buộc liệt kê 2-3 thay đổi |
| Bỏ phần điểm đáng chú ý | Mỗi mục đều có 2-3 điểm rút ra — đây là phần buổi trình bày tốn ít chữ nhất nhưng có giá trị nhất |

---

## Sau khi xong Mục D

Đã đủ 4 mục (A → D). Chuyển sang `worksheet/04-FINAL-economics-sheet.md` để gộp toàn bộ thành **bảng kinh tế tổng** — đây là file deliverable cuối cùng nộp lên LMS.

Khi gộp, giữ đúng thứ tự: A (Cost) → B (Pricing) → C (Value / ROI) → D (Stress Test + Quyết định).
