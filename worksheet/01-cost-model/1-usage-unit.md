---
artifact: 1 — Xác định đơn vị AI làm việc (Usage Unit) + ước tính khối lượng
buoc: 1 — Cost Model
phase: Định nghĩa đơn vị AI làm việc + ước tính khối lượng
thoi-gian: 15 phút
input: 00-context.md + đề bài được giao + prompts/01-define-usage-unit.md
nop-cuoi: Không — đây là file trung gian (chỉ section A trong `04-FINAL-economics-sheet.md` là bản nộp)
---

# 1 — Định nghĩa đơn vị AI làm việc + ước tính khối lượng

**Mục tiêu**: trước khi tính bất kỳ con số chi phí nào, nhóm phải biết rõ **AI làm việc gì trong một lần chạy** và **mỗi tháng AI chạy bao nhiêu lần**.

Vì sao quan trọng: nếu không có đơn vị AI làm việc (gọi là *Usage Unit* trong tiếng Anh), thì các con số sau — chi phí mỗi lần chạy, giá trị mỗi lần chạy, chi phí mỗi tháng — đều không có nền tảng. Đây là "đơn vị nguyên tử" của bài toán kinh tế AI.

**Quy tắc**: không có đơn vị AI làm việc rõ ràng = không có Cost Model.

---

## Tổng thời gian 15 phút

| Phần | Thời gian | Việc cần làm |
|---|---|---|
| A | 5 phút | Mỗi người tự nghĩ ra 1 phương án — sau đó cặp chọn 1 |
| B | 5 phút | Kiểm tra phương án đã chọn không rơi vào các lỗi hay mắc |
| C | 5 phút | Mô tả chi tiết phương án + ước tính khối lượng |

---

## Phần A — Tự nghĩ phương án

### Trước khi viết, mỗi người tự hỏi

- Trong quy trình ở đề bài, AI chen vào ở khâu nào?
- Đầu ra của AI ở khâu đó nhìn như thế nào (một chữ phân loại / một đoạn văn / một quyết định / một bảng dữ liệu)?
- Một lần AI chạy có thực sự đếm được không, hay là một thứ mơ hồ?

### Một phương án đơn vị AI làm việc hợp lệ phải qua 3 câu kiểm tra

1. **Đếm được không?** — Có thể đếm "AI đã làm việc này X lần" mà không tranh cãi.
2. **Có tốn token không?** — Một lần chạy có gọi sang API (giao diện gọi AI từ phần mềm), tức có chi phí thật.
3. **Người dùng có thấy giá trị không?** — Một lần AI làm việc này có rút ngắn thời gian hoặc cải thiện chất lượng cho người dùng cụ thể nào?

Nếu cả 3 câu = Có → phương án hợp lệ.

### Phương án người 1

**Tên ngắn của đơn vị**:

```text
(điền vào đây)
```

| Câu kiểm tra | Trả lời |
|---|---|
| Đếm được không? | _ _ _ |
| Có tốn token không? | _ _ _ |
| Người dùng có thấy giá trị không? | _ _ _ |

### Phương án người 2

**Tên ngắn của đơn vị**:

```text
(điền vào đây)
```

| Câu kiểm tra | Trả lời |
|---|---|
| Đếm được không? | _ _ _ |
| Có tốn token không? | _ _ _ |
| Người dùng có thấy giá trị không? | _ _ _ |

### Cặp chọn phương án nào?

```text
(điền tên ngắn vào đây)
```

**Lý do chọn phương án này** (so với phương án kia):

```text
(điền vào đây)
```

---

## Phần B — Đối chiếu với các lỗi hay mắc

Đọc bảng dưới, rồi tự đánh giá xem phương án của nhóm có rơi vào lỗi nào không.

| Lỗi | Ví dụ sai | Vì sao sai |
|---|---|---|
| **Quá rộng** | "AI hỗ trợ team support" | Không đếm được — không biết "hỗ trợ" tính một lần hay nhiều lần |
| **Quá hẹp** | "1 token AI sinh ra" | Đếm được nhưng người dùng không trả tiền theo token |
| **Không phải đơn vị nhỏ nhất** | "1 ticket được giải quyết" | Một ticket có thể gọi AI nhiều lần (tìm tài liệu, viết nháp, sửa lại). Đơn vị nhỏ nhất phải là một lần AI chạy |
| **Trộn lẫn việc người với việc AI** | "1 ca trực support" | Bao gồm cả công việc người làm không liên quan đến AI |
| **Đúng kỹ thuật, sai góc nhìn kinh doanh** | "1 lần gọi API" | Đúng kỹ thuật nhưng người mua (CTO, VP) không hiểu vì sao họ trả tiền cho "lần gọi API" |

### Phương án của nhóm có rơi vào lỗi nào không?

```text
(điền vào đây — nếu có, sửa lại trước khi sang Phần C)
```

---

## Phần C — Mô tả chi tiết đơn vị + ước tính khối lượng

### C.1 — Mô tả chi tiết

**Tên đơn vị AI làm việc**:

```text
(điền tên ngắn — vd: "1 bản nháp trả lời ticket")
```

**Mô tả 2-3 câu** *(AI nhận đầu vào gì, sinh đầu ra gì, đầu ra đi đâu)*:

```text
(điền vào đây)
```

**AI chạy khi nào?** *(người dùng bấm nút / tự động khi có sự kiện / theo lịch / ...)*:

```text
(điền vào đây)
```

**Đầu vào dự kiến trong một lần chạy** *(văn bản nào / dữ liệu nào, kích thước ước lượng)*:

```text
(điền vào đây)
```

**Đầu ra dự kiến trong một lần chạy** *(văn bản / số / nhãn, kích thước ước lượng)*:

```text
(điền vào đây)
```

### C.2 — Khối lượng

Mở đề bài, lấy các số sau:

| Số liệu | Giá trị | Lấy từ trường nào trong đề bài |
|---|---|---|
| Người dùng trong nhóm thử nghiệm | _ _ _ | Trường 8 — Ngân sách / Thời gian pilot |
| Tổng đội | _ _ _ | Trường 1 — Bối cảnh doanh nghiệp |
| Khối lượng mỗi ngày của toàn đội | _ _ _ | Trường 1 hoặc Trường 7 — Chỉ số nền |

Tính khối lượng mỗi ngày của nhóm thử nghiệm:

```text
Khối lượng mỗi ngày = (Người dùng pilot / Tổng đội) × Khối lượng mỗi ngày toàn đội
```

→ Số tính ra:

```text
(điền vào đây — vd: 160 việc/ngày)
```

Tính khối lượng mỗi tháng (1 tháng làm việc = 22 ngày):

```text
Khối lượng mỗi tháng = Khối lượng mỗi ngày × 22
```

→ Số tính ra:

```text
(điền vào đây — vd: 3,520 việc/tháng)
```

> **Lưu ý quan trọng**: dùng **khối lượng của nhóm thử nghiệm**, không phải của toàn đội. Đây là lỗi nhiều nhóm mắc — họ tính cost theo khối lượng toàn đội nhưng pilot chỉ chạy với một nhóm nhỏ.

---

## Phần D — Kiểm tra hợp lý trước khi sang Phase 2

Trước khi sang `2-cost-research.md`, đánh dấu các ô đã xong:

- [ ] Đơn vị qua 3 câu kiểm tra (đếm được, tốn token, có giá trị)
- [ ] Đơn vị không quá rộng / quá hẹp / lẫn việc người
- [ ] Khối lượng tính cho **nhóm thử nghiệm**, không phải toàn đội
- [ ] Số ngày làm việc dùng là 22
- [ ] Khối lượng cuối là một số cụ thể, không phải "khoảng vài nghìn"

### Câu hỏi cảm tính

Nhìn số khối lượng vừa tính ra: có khớp với quy mô đề bài không?

- Vd: đề bài 800 ticket/ngày toàn đội, pilot 5/25 → 160 ticket/ngày cho pilot là hợp lý.
- Vd: đề bài 2 triệu bài/ngày, pilot 5/15 reviewer → ~6,667 lần kiểm tra mỗi ngày cho pilot là hợp lý.

Câu trả lời của nhóm:

```text
(điền vào đây)
```

---

## Phần E — Gợi ý chuẩn bị cho Phase 2 (Cost Research)

Trước khi sang phần tra giá, suy nghĩ trước về kích thước token:

| Loại việc | Số token đầu vào điển hình | Số token đầu ra điển hình |
|---|---|---|
| Phân loại / gán nhãn | 200–500 | 50–100 |
| Viết bản nháp ngắn | 800–1,500 | 300–500 |
| Tóm tắt / phân tích văn bản dài | 5,000–20,000 | 1,000–3,000 |

Nhóm dự đoán đơn vị của mình rơi vào nhóm nào? Số token đầu vào / đầu ra dự kiến bao nhiêu?

```text
(điền vào đây — vd: "Bản nháp trả lời ticket, đầu vào ~1,200 tokens, đầu ra ~400 tokens")
```

Câu trả lời này sẽ dùng để tra giá ở Phase 2.

---

## Câu hỏi mở để nhóm hỏi AI ở Phase 2

Nghĩ trước 2-3 câu nhóm sẽ hỏi AI hỗ trợ ở Phase 2:

```text
1. (điền vào đây — vd: "Cần dùng vector DB cho phần tìm tài liệu không, nếu có giá bao nhiêu?")
2.
3.
```

---

Sang bước tiếp: mở `2-cost-research.md` để tra giá và tính chi phí cho mỗi lần AI chạy.
