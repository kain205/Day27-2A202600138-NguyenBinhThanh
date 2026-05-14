---
artifact: 3 — Chốt Cost Model (Mục A của bảng kinh tế)
buoc: 1 — Cost Model
phase: Chốt mục A
thoi-gian: 10 phút
input: 1-usage-unit.md + 2-cost-research.md
nop-cuoi: Có — mục A sẽ được dán vào `04-FINAL-economics-sheet.md` để nộp
---

# 3 — Chốt Cost Model (Mục A của bảng kinh tế)

**Mục tiêu**: gộp các con số đã có từ `1-usage-unit.md` và `2-cost-research.md` thành **Mục A — Cost Model** với đầy đủ 10-15 trường + công thức tính chi phí mỗi tháng.

Đây là file cuối của Bước 1 trong Lab. Người chấm sẽ đọc Mục A này song song với 3 mục còn lại trong file gộp `04-FINAL-economics-sheet.md`.

Vì sao quan trọng: nếu Mục A không gãy, mọi tính toán của Bước 2 (giá trị / ROI) và Bước 3 (kịch bản xấu) đều có nền tảng. Nếu Mục A lung lay, các bước sau cũng lung lay theo.

**Quy tắc khi điền**:

- Mỗi con số đều phải có công thức, nguồn, hoặc lý do — không có số "trên trời rơi xuống".
- Cấm dùng "khoảng", "tầm", "đại loại" — phải là một số cụ thể.
- Khi cần công thức chi tiết, mở `1-usage-unit.md` (phần khối lượng) và `2-cost-research.md` (phần chi phí từng thành phần).

---

## Tổng thời gian 10 phút

| Phần | Thời gian | Việc cần làm |
|---|---|---|
| A.0 | 1 phút | Điền thông tin nhóm |
| A.1 → A.6 | 6 phút | Điền 6 mục con: đơn vị tính, khối lượng, API, công cụ phụ trợ, người kiểm, setup |
| A.7 | 2 phút | Áp công thức 4 thành phần → chi phí mỗi tháng |
| A.8 | 1 phút | Kiểm tra so với ngân sách trong đề bài |

---

## Thông tin nhóm

Trước khi điền các mục con, ghi thông tin nhận diện. Người chấm dùng cho việc đối chiếu.

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

- **Phiên bản** *(v1 cho lần nộp đầu, v2 nếu nhóm sửa lại sau phản hồi)*:

```text
(điền vào đây)
```

---

## Mục A — Cost Model

### A.1 — Đơn vị AI làm việc

Trả lời "AI làm việc gì trong một lần chạy". Lấy từ `1-usage-unit.md` phần C.1.

| Trường | Giá trị |
|---|---|
| Tên ngắn của đơn vị | (điền vào đây) |
| Mô tả 1-2 câu *(AI nhận đầu vào gì, sinh đầu ra gì, đi đâu)* | (điền vào đây) |
| Đếm được không? | (điền vào đây) |
| Có tốn token không? | (điền vào đây) |
| Người dùng có thấy giá trị không? | (điền vào đây) |

### A.2 — Khối lượng

Lấy từ `1-usage-unit.md` phần C.2. Nhắc lại: khối lượng tính cho **nhóm thử nghiệm**, không phải toàn đội.

| Trường | Giá trị | Công thức / Nguồn |
|---|---|---|
| Người dùng trong nhóm thử nghiệm | (điền vào đây) | Trường 8 trong đề bài |
| Tổng đội | (điền vào đây) | Trường 1 trong đề bài |
| Khối lượng mỗi ngày của toàn đội | (điền vào đây) việc/ngày | Trường 1 hoặc Trường 7 |
| Khối lượng mỗi ngày của nhóm thử nghiệm | (điền vào đây) việc/ngày | (Người thử / Tổng đội) × Khối lượng toàn đội |
| Khối lượng mỗi tháng | (điền vào đây) việc/tháng | Khối lượng mỗi ngày × 22 ngày làm việc |

### A.3 — Chi phí API

Lấy từ `2-cost-research.md` phần B. Mọi giá phải có đường dẫn trang giá nhà cung cấp.

| Trường | Giá trị | Nguồn |
|---|---|---|
| Nhà cung cấp chính | (điền vào đây) | (dán đường dẫn trang giá) |
| Mô hình chọn | (điền vào đây) | (dán đường dẫn trang giá) |
| Giá đầu vào ($/1M token) | $(điền vào đây) | (dán đường dẫn) |
| Giá đầu ra ($/1M token) | $(điền vào đây) | (dán đường dẫn) |
| Số token đầu vào mỗi lần chạy | (điền vào đây) | Ước tính từ loại việc |
| Số token đầu ra mỗi lần chạy | (điền vào đây) | Ước tính từ loại việc |
| Chi phí API mỗi lần chạy | $(điền vào đây) | (in × giá_in + out × giá_out) / 1.000.000 |

### A.4 — Chi phí công cụ phụ trợ

Lấy từ `2-cost-research.md` phần C. Nếu không cần một công cụ → ghi `0` và lý do "không cần", đừng để trống.

| Trường | Giá trị | Nguồn / Lý do |
|---|---|---|
| Cơ sở dữ liệu vector *(Pinecone / Qdrant / pgvector / không cần)* | $(điền vào đây) /tháng | (điền vào đây) |
| Giám sát chất lượng *(Langfuse / Helicone / không cần)* | $(điền vào đây) /tháng | (điền vào đây) |
| Điều phối quy trình *(n8n / Zapier / tự viết / không cần)* | $(điền vào đây) /tháng | (điền vào đây) |
| Công cụ phụ trợ khác | $(điền vào đây) /tháng | (điền vào đây) |
| **Tổng công cụ phụ trợ mỗi tháng** | **$(điền vào đây)** | Cộng 4 dòng trên |

### A.5 — Chi phí người kiểm

Áp dụng nếu đề bài có ràng buộc người kiểm trước khi AI gửi đầu ra. Nếu đề bài cho phép AI tự gửi → điền `0` và ghi rõ "đề bài cho phép AI tự gửi".

| Trường | Giá trị | Công thức / Lý do |
|---|---|---|
| Lương người kiểm mỗi giờ *(đã gồm phụ cấp = lương cơ bản × 1.3-1.5)* | $(điền vào đây) /giờ | Lấy từ đề bài hoặc giả định theo ngành |
| Thời gian kiểm một việc | (điền vào đây) phút | Ước tính từ ràng buộc trong đề bài |
| Chi phí kiểm mỗi việc | $(điền vào đây) /việc | (phút / 60) × lương giờ |
| Chi phí kiểm mỗi tháng | $(điền vào đây) /tháng | Khối lượng mỗi tháng × chi phí kiểm mỗi việc |

### A.6 — Chi phí setup (chia đều theo tháng)

Setup là chi phí một lần (tích hợp + kiểm tra an ninh + viết câu lệnh AI lần đầu). Chia đều cho số tháng thử nghiệm để tính chi phí mỗi tháng.

| Trường | Giá trị | Lý do |
|---|---|---|
| Chi phí setup một lần | $(điền vào đây) | Tích hợp + kiểm tra an ninh + viết và tinh chỉnh câu lệnh AI |
| Thời gian thử nghiệm | (điền vào đây) tháng | Trường 8 trong đề bài, chia 30 |
| Chi phí setup chia đều mỗi tháng | $(điền vào đây) /tháng | Setup / số tháng thử nghiệm |

### A.7 — Công thức chi phí mỗi tháng

Tổng chi phí mỗi tháng gồm 4 thành phần. Áp công thức cho nhóm.

**Công thức gốc**:

```text
Chi phí AI mỗi tháng
  = (Khối lượng mỗi tháng × Chi phí API mỗi lần)   [API]
  + Tổng công cụ phụ trợ mỗi tháng                  [Công cụ phụ trợ]
  + (Khối lượng mỗi tháng × Chi phí kiểm mỗi việc)  [Người kiểm]
  + Chi phí setup chia đều mỗi tháng                [Setup]
```

**Tính cụ thể cho nhóm**:

```text
Chi phí AI mỗi tháng
  = ((điền vào đây) × $(điền vào đây))   = $(điền vào đây)   [API]
  + $(điền vào đây)                                            [Công cụ phụ trợ]
  + ((điền vào đây) × $(điền vào đây))   = $(điền vào đây)   [Người kiểm]
  + $(điền vào đây)                                            [Setup]
                                          ────────────
                                          = $(điền vào đây) /tháng (TỔNG)
```

### A.8 — Đối chiếu với ngân sách

| Trường | Giá trị |
|---|---|
| Tổng chi phí mỗi tháng | $(điền vào đây) |
| Ngân sách thử nghiệm mỗi tháng *(trường 8 trong đề bài)* | $(điền vào đây) |
| % so với ngân sách | (điền vào đây) % |
| Tình trạng | (Trong ngân sách / Vượt ngân sách) |

**Nếu vượt ngân sách**: nhóm sẽ làm gì? *(vd: dùng mô hình rẻ hơn cho loại việc đơn giản / giảm khối lượng thử nghiệm / đàm phán giá doanh nghiệp với nhà cung cấp)*

```text
(điền vào đây)
```

---

## 2-3 điểm đáng chú ý sau khi tính

Sau khi tính xong toàn bộ Mục A, nhóm tự rút ra 2-3 điểm đáng chú ý về cấu trúc chi phí. Đây là phần ý nghĩa nhất khi trình bày — không phải con số, mà là **hiểu cái gì đang điều khiển chi phí**.

Trước khi viết, tự hỏi:

- Thành phần nào (API / công cụ phụ trợ / người kiểm / setup) chiếm phần lớn nhất? Có ngạc nhiên không?
- Có chi phí nào cao hơn / thấp hơn dự đoán ban đầu của nhóm không?
- Nếu phải cắt một thành phần, cắt cái nào sẽ ảnh hưởng nhỏ nhất đến chất lượng?

→ Viết 2-3 điểm:

```text
1. (điền vào đây)
2. (điền vào đây)
3. (điền vào đây)
```

---

## Bảng kiểm trước khi gộp vào file FINAL

- [ ] Đơn vị AI làm việc qua 3 câu kiểm tra, có mô tả 1-2 câu rõ ràng.
- [ ] Khối lượng tính cho **nhóm thử nghiệm**, không phải toàn đội.
- [ ] Mỗi giá API có đường dẫn trang giá nhà cung cấp.
- [ ] Chi phí API tính theo công thức token, không ghi "ước tính".
- [ ] Mỗi công cụ phụ trợ có tên + giá tháng (hoặc lý do "không cần").
- [ ] Chi phí người kiểm tính theo phút × lương giờ (nếu đề bài có ràng buộc kiểm).
- [ ] Chi phí setup được chia đều theo số tháng thử nghiệm.
- [ ] Công thức A.7 có 4 dòng cộng lại bằng tổng.
- [ ] Có đối chiếu với ngân sách trong đề bài.
- [ ] Có 2-3 điểm đáng chú ý đã viết ra.

Số trường đã điền có số cụ thể: ___ / 30+ trường (yêu cầu tối thiểu 25).

---

## Những lỗi hay mắc (kiểm tra lần cuối)

| Đừng | Thay vào đó |
|---|---|
| "Chi phí mỗi việc khoảng $0.01" | "$0.0084 = (800 × $3 + 400 × $15) / 1.000.000" |
| Quên chi phí người kiểm | Nếu đề bài có ràng buộc 100% người kiểm → đây thường là thành phần lớn nhất |
| Dùng khối lượng toàn đội | Dùng khối lượng nhóm thử nghiệm *(vd: 5/25 × 800 = 160 việc/ngày, không phải 800)* |
| Công cụ phụ trợ = $0 toàn bộ | Ít nhất phải có giám sát chất lượng — bậc miễn phí cũng phải ghi vào và ghi $0 |
| Setup = $0 | Tích hợp + viết câu lệnh AI lần đầu luôn tốn thời gian của lập trình viên |
| Chi phí mỗi việc < $0.0001 | Kiểm tra lại — mô hình rẻ nhất cho việc phân loại cũng khoảng $0.000135 mỗi lần chạy |
| Chi phí mỗi việc > $50 cho một việc đơn giản | Có thể chọn mô hình quá lớn — thử mô hình rẻ hơn |
| Không ghi đường dẫn trang giá | Mỗi giá API phải có đường dẫn trang giá nhà cung cấp |

---

## Sau khi xong Mục A

Mục A đã chốt. Chuyển sang `worksheet/02-pricing-value/` để dựng Mục B (Pricing / Access) và Mục C (Value / ROI).

Chi phí một mình chưa trả lời được "có nên triển khai không" — cần ghép với giá trị để tính ROI ở Bước 2.
