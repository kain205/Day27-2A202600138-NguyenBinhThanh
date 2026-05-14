---
artifact: 2 — Tra giá nhà cung cấp + tính chi phí mỗi lần AI chạy
buoc: 1 — Cost Model
phase: Tra giá thật + tính chi phí
thoi-gian: 15 phút
input: 00-context.md + đề bài + 1-usage-unit.md + prompts/02-cost-formula.md
nop-cuoi: Không — file trung gian
---

# 2 — Tra giá nhà cung cấp + tính chi phí mỗi lần AI chạy

**Mục tiêu**: tự tra trang giá của các nhà cung cấp AI, ước tính chi phí mỗi lần AI chạy, rồi tổng hợp đủ 4 thành phần chi phí (API + tooling + người kiểm + setup).

Vì sao quan trọng: bài giảng **không cho sẵn bảng giá**. Trong thực tế, người làm sản phẩm phải tự tra giá — và giá AI thay đổi rất nhanh. Đây là kỹ năng phải tự rèn.

**Quy tắc**: không có đường dẫn trang giá = không có con số chi phí.

---

## Tổng thời gian 15 phút

| Phần | Thời gian | Việc cần làm |
|---|---|---|
| A | 5 phút | Tra giá 1-2 nhà cung cấp chính + lưu đường dẫn |
| B | 5 phút | Tính chi phí API cho một lần chạy theo công thức token |
| C | 5 phút | Cộng đủ 4 thành phần (API + tooling + người kiểm + setup) |

---

## Phần A — Tra giá nhà cung cấp

### Bảng tham chiếu nhanh (chỉ dùng để khởi đầu)

Bảng dưới là **điểm khởi đầu** — không thay thế việc click vào trang giá chính chủ. Giá AI thay đổi vài tháng một lần, có khi nhanh hơn.

| Nhà cung cấp | Mô hình | Đầu vào ($/1M token) | Đầu ra ($/1M token) |
|---|---|---|---|
| Anthropic | Claude 3.5 Sonnet | $3.00 | $15.00 |
| OpenAI | GPT-4o | $2.50 | $10.00 |
| OpenAI | GPT-4o-mini | $0.15 | $0.60 |
| Google | Gemini 1.5 Pro | $1.25 | $5.00 |

> **Lưu ý**: số trên là chuẩn 2025-Q1. Bắt buộc click vào trang giá của nhà cung cấp để xác minh trước khi điền vào bảng. Một trường hợp thật: Salesforce đổi giá AI 3 lần trong 18 tháng.

### A.1 — Nhà cung cấp chính nhóm chọn

Nhóm đã chọn nhà cung cấp ở `00-context.md` phần 7. Mở trang giá của họ và lấy số.

**Tên nhà cung cấp**:

```text
(điền vào đây)
```

**Tên mô hình cụ thể**:

```text
(điền vào đây)
```

**Đường dẫn trang giá** *(URL chính chủ — nếu trang hay đổi, chụp màn hình kèm theo)*:

```text
(điền vào đây — vd: https://www.anthropic.com/pricing)
```

### A.2 — Bảng giá tra được

Lấy giá theo định dạng **USD trên 1 triệu token**. Nếu trang giá ghi đơn vị khác (vd: per 1K token), tự quy đổi.

Trước khi điền, tự hỏi:

- Mô hình có nhiều tier không? (vd: Standard / Batch / Long-context — giá có thể khác).
- Đầu vào (input) và đầu ra (output) có thể có giá rất khác nhau.
- Có giá riêng cho cache/prompt caching không?

| Nhà cung cấp | Mô hình | Đầu vào ($/1M token) | Đầu ra ($/1M token) | Ghi chú |
|---|---|---|---|---|
| (điền) | (điền) | $___ | $___ | (vd: tier tiêu chuẩn) |
| (điền) | (điền) | $___ | $___ | (vd: tier rẻ hơn để dự phòng) |
| (điền) | (điền) | $___ | $___ | (vd: phương án backup) |

**Mô hình nhóm chọn cuối cùng**:

```text
(điền vào đây)
```

**Lý do chọn** *(chất lượng / giá / tốc độ / khu vực dữ liệu / phù hợp loại việc)*:

```text
(điền vào đây)
```

---

## Phần B — Tính chi phí API cho một lần chạy

### B.1 — Ước tính số token

Quy tắc đổi nhanh:

- 1 token ≈ 4 ký tự tiếng Anh ≈ 1.5 từ tiếng Việt.
- Ticket dài 500 từ tiếng Anh ≈ 750 token.

**Token đầu vào dự kiến** *(prompt + ngữ cảnh + system prompt + dữ liệu kèm)*:

```text
(điền số — vd: 6,000)
```

Lý do ra con số trên *(liệt kê các thành phần)*:

```text
(điền vào đây — vd: "Ticket 500 từ ≈ 750 token + 3 bài KB ~1,500 từ mỗi bài ≈ 4,500 token + system prompt 750 token = ~6,000")
```

**Token đầu ra dự kiến** *(phản hồi của AI)*:

```text
(điền số — vd: 400)
```

Lý do ra con số trên:

```text
(điền vào đây)
```

### B.2 — Công thức chi phí API mỗi lần chạy

```text
Chi phí API mỗi lần chạy = (token đầu vào × giá đầu vào + token đầu ra × giá đầu ra) / 1,000,000
```

Tính cho nhóm:

```text
Chi phí API = (___ × $___ + ___ × $___) / 1,000,000
            = $___
            ≈ $0.0___ /lần chạy
```

---

## Phần C — Cộng đủ 4 thành phần chi phí

Chi phí mỗi việc của AI không chỉ là API. Có 4 thành phần — bỏ qua một thành phần = ước tính lệch.

### C.1 — Vector DB / Embedding (nếu có dùng RAG)

Trước khi điền, tự hỏi:

- Đơn vị AI làm việc của nhóm có cần tra cứu tài liệu không?
- Nếu có, dùng cách nào để index tài liệu?

| Trường | Giá trị |
|---|---|
| Tên công cụ *(Pinecone / Qdrant / Weaviate / pgvector / không cần)* | (điền) |
| Giá theo tháng (gói nhỏ nhất phù hợp pilot) | $___ /tháng |
| Đường dẫn trang giá | (điền) |

### C.2 — Giám sát / Logging

Mục tiêu: log lại mọi lần AI chạy để debug và theo dõi chất lượng.

| Trường | Giá trị |
|---|---|
| Tên công cụ *(Langfuse / Langsmith / Helicone / không cần)* | (điền) |
| Giá theo tháng | $___ /tháng |
| Đường dẫn trang giá | (điền) |

### C.3 — Điều phối workflow

Nếu cần ghép nhiều bước hoặc gọi nhiều API:

| Trường | Giá trị |
|---|---|
| Tên công cụ *(n8n / Zapier / custom code / không cần)* | (điền) |
| Giá theo tháng | $___ /tháng |
| Đường dẫn trang giá | (điền) |

### C.4 — Chi phí người kiểm

Nếu đề bài có ràng buộc người kiểm trước khi gửi (vd: 100% review), đây thường là phần lớn nhất trong tổng chi phí.

Trước khi điền, tự hỏi:

- Đề bài có nêu lương người kiểm không? Nếu không, dùng mức bao nhiêu cho hợp lý?
- Lương cơ bản thôi hay đã cộng phụ cấp + chi phí gián tiếp?
- Một lần kiểm mất bao nhiêu phút?

| Trường | Giá trị |
|---|---|
| Lương người kiểm theo giờ | $___ /giờ |
| Lý do chọn mức lương này | (điền — vd: "Đề bài cho $20/giờ base × 1.3 loaded") |
| Thời gian kiểm một việc | ___ phút |
| Chi phí kiểm một việc = (phút / 60) × lương giờ | $___ /việc |

> **Lưu ý về "loaded rate"**: lương thực tế đội ngũ bao gồm cả phụ cấp, bảo hiểm, chi phí văn phòng. Hệ số 1.3-1.5 lần lương cơ bản là mức bảo thủ thường dùng.

### C.5 — Chi phí setup (phân bổ)

Setup là chi phí một lần để dự án chạy được: tích hợp, security review, training, tinh chỉnh prompt. Không thể tính cả cục vào tháng đầu — phải phân bổ đều cho thời gian pilot.

Trước khi điền, tự hỏi:

- Nhóm cần bao nhiêu công sức kỹ thuật để tích hợp AI vào quy trình hiện có?
- Có cần review về bảo mật + tuân thủ không?
- Bao nhiêu thời gian thử nghiệm + tinh chỉnh prompt cho đến khi đạt chất lượng?

| Trường | Giá trị |
|---|---|
| Tổng chi phí setup một lần | $___ |
| Lý do ra con số này *(vd: "1 engineer × 2 tuần × $4,000/tuần = $8,000")* | (điền) |
| Thời gian pilot | ___ tháng |
| Setup phân bổ mỗi tháng = Tổng / số tháng pilot | $___ /tháng |

---

## Phần D — Tổng chi phí mỗi lần AI chạy

Sau khi có cả 4 thành phần, tổng hợp lại:

### D.1 — Chi phí tooling phân bổ theo việc

Nếu tooling tính theo tháng (vd: $200/tháng), chia ngược ra theo khối lượng để có chi phí mỗi việc:

```text
Tooling mỗi việc = (Tổng tooling tháng) / (Khối lượng tháng)
                 = $___ / ___ việc
                 = $0.0___ /việc
```

### D.2 — Chi phí người kiểm mỗi việc

Đã có ở C.4:

```text
Người kiểm mỗi việc = $___ /việc
```

### D.3 — Tổng chi phí mỗi việc

```text
Tổng chi phí mỗi việc = API + Tooling + Người kiểm
                      = $___ + $___ + $___
                      = $___ /việc
```

---

## Phần E — Đối chiếu với mức thông thường

Bảng dưới giúp kiểm tra hợp lý. Nếu con số của nhóm lệch xa, rà lại bước ước tính token hoặc chọn mô hình.

| Loại việc | Chi phí mỗi việc thông thường | Lý do |
|---|---|---|
| Phân loại / gán nhãn đơn giản | $0.001 – $0.01 | Token ngắn, mô hình rẻ |
| Sinh bản nháp ngắn (1 reply) | $0.01 – $0.05 | Token vừa, mô hình trung |
| Phân tích tài liệu dài | $0.10 – $0.50 | Token dài, mô hình mạnh |
| Agent nhiều bước (search + reason + act) | $0.50 – $5.00 | Nhiều lần gọi API |
| Long context (hợp đồng dài, audit) | $1.00 – $20.00 | 100K+ token đầu vào |

**Con số của nhóm rơi vào nhóm nào trên đây? Có khớp với loại việc không?**

```text
(điền vào đây)
```

---

## Phần F — Kiểm tra lại trước khi sang bản FINAL

- [ ] Có đường dẫn trang giá cho mỗi nhà cung cấp.
- [ ] Đã chọn 1 mô hình cụ thể (không "mô hình nào đó của OpenAI").
- [ ] Chi phí mỗi việc là số cụ thể (vd: $0.024), không "khoảng 0.02".
- [ ] Nếu đề bài có ràng buộc người kiểm → đã tính chi phí người kiểm.
- [ ] Mỗi công cụ tooling có tên + giá tháng + đường dẫn.
- [ ] Setup được phân bổ theo số tháng pilot, không gán hết vào tháng 1.

---

## Phần G — Cẩn thận: AI có thể bịa giá

Nếu nhóm dùng AI hỗ trợ để gợi ý giá, **luôn click vào trang giá chính chủ để xác minh**.

Các lỗi AI hay bịa:

- AI có thể nói "Claude 3.5 Sonnet $5/1M input" — sai. Phải kiểm trên anthropic.com/pricing.
- AI có thể nói giá của mô hình mới (Claude 4, GPT-5) — thường bịa vì training data cũ.
- AI có thể quên tính một thành phần (vd: chỉ tính API, quên người kiểm).
- Nếu chi phí mỗi việc < $0.001 hoặc > $50 cho việc trung bình → gần như chắc chắn sai. Rà lại token estimate.

---

## Phần H — Câu hỏi mang sang bản FINAL

Nghĩ trước 2-3 câu hỏi nhóm muốn AI giúp trả lời ở bước tổng hợp FINAL:

```text
1. (điền — vd: "Setup cost phân bổ 3 tháng pilot có hợp lý không, hay nên phân bổ dài hơn vì hệ thống sẽ dùng sau pilot?")
2.
3.
```

---

Sang bước tiếp: mở `3-FINAL-cost-model.md` để tổng hợp tất cả vào Section A của Economics Sheet.
