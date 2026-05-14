# Day 27 — Kinh tế sản phẩm AI: Đơn vị tính, chi phí và định giá

Ngày 27 là ngày BUILD: mỗi cặp 2 người nhận **một đề bài cố định**, tự dựng **Bảng kinh tế sản phẩm AI** (gồm 4 phần — chi phí, định giá, giá trị, kịch bản xấu kèm quyết định cuối), rồi trình bày 6 phút cuối buổi.

Câu hỏi dẫn dắt cả ngày:

> "Nếu người dùng thật sự xài giải pháp AI này, **kinh tế và rủi ro có đứng vững không**?"

Khác Ngày 26 (phân tích chiến lược của sản phẩm AI đã có sẵn), Ngày 27 buộc nhóm **tự dựng kinh tế từ con số 0** cho một tình huống cụ thể đã được giao. Đầu ra cuối cùng là một quyết định: GO / CONDITIONAL / NO-GO kèm điều kiện rõ ràng.

Quy tắc xuyên suốt cả ngày: **không có công thức hoặc nguồn giá rõ ràng = không có số trên giấy**. Mọi con số phải truy ngược về đề bài hoặc về trang giá thật của nhà cung cấp AI (URL phải mở được).

---

## Cấu trúc một ngày

```text
09:00-10:00  Lý thuyết 60'      Khung Chi phí / Định giá / Giá trị + Ví dụ chạy mẫu (Support Copilot)
10:00-10:10  Nghỉ giữa giờ
10:10-10:50  Lab Bước 1 — 40'   Đơn vị AI làm việc + Mô hình chi phí (Phần A)
10:50-11:30  Lab Bước 2 — 40'   Định giá/Truy cập + Giá trị/ROI (Phần B + C)
11:30-12:10  Lab Bước 3 — 40'   5 kịch bản xấu + Quyết định cuối (Phần D)
12:10-12:55  Trình bày 45'      4 cặp × ~10' (3' trình bày + 7' hỏi đáp)
12:55-13:00  Chốt buổi 5'       Tóm tắt + giới thiệu Ngày 28
```

60 phút lý thuyết trang bị khung suy luận. 120 phút Lab là phần chính. 45 phút trình bày rút ra bài học so sánh giữa các đề bài khác nhau.

---

## Nộp bài thế nào? (đọc trước khi vào Lab)

### Tên kho GitHub

Cú pháp: **`Day27-MãNhóm`**

Ví dụ: `Day27-G001`, `Day27-G045`, `Day27-A1`.

Kho mẫu của giảng viên: <https://github.com/VinUni-AI20k/Day27-Track01-AI-Product-Economics>

### Cần nộp những file gì?

Mỗi nhóm tạo **một kho GitHub công khai**, đưa toàn bộ thư mục `worksheet/` lên kho theo đúng cấu trúc dưới, rồi nộp đường dẫn qua LMS.

```text
Day27-MãNhóm/                                       ← kho GitHub công khai
│
├── README.md                                       ← Thành viên cặp + đường dẫn tới file CHỐT (xem mẫu dưới)
│
└── worksheet/
    ├── 00-context.md                               ← Ngữ cảnh nhóm + đề bài đã được giao (đã điền)
    │
    ├── 01-cost-model/
    │   ├── 1-usage-unit.md                         ← File trung gian: định nghĩa đơn vị AI làm việc + khối lượng
    │   ├── 2-cost-research.md                      ← File trung gian: tra giá nhà cung cấp + chi phí mỗi lần chạy
    │   └── 3-FINAL-cost-model.md                   🎯 Phần A của Bảng kinh tế
    │
    ├── 02-pricing-value/
    │   ├── 1-attribution-autonomy.md               ← File trung gian: định vị trên ma trận 2×2
    │   ├── 2-pricing-model-choice.md               ← File trung gian: chọn cách định giá + chọn đơn vị tính tiền
    │   └── 3-FINAL-pricing-value-roi.md            🎯 Phần B + C của Bảng kinh tế
    │
    ├── 03-stress-test/
    │   ├── 1-scenario-table.md                     ← File trung gian: 5 kịch bản xấu + kịch bản kết hợp
    │   ├── 2-verdict-draft.md                      ← File trung gian: bản nháp quyết định + điều kiện
    │   └── 3-FINAL-stress-test-verdict.md          🎯 Phần D của Bảng kinh tế
    │
    └── 04-FINAL-economics-sheet.md                 🎯🎯 FILE TỔNG — gộp Phần A + B + C + D
```

🎯 = các phần của Bảng kinh tế (người chấm xem). Các file trung gian là **dấu vết quá trình** — phải nộp kèm để người chấm thấy nhóm đã đi qua đủ các bước suy luận.

🎯🎯 = FILE TỔNG — đây là sản phẩm cuối, người chấm sẽ xem file này trước.

### README đầu kho phải có gì?

Sao chép mẫu này vào `README.md` ở gốc kho rồi điền:

```markdown
# Day 27 — Mã nhóm [G___]

## Thành viên cặp

| # | Mã học viên | Họ tên đầy đủ |
|---|-------------|---------------|
| 1 | A20-XXXXX   | Nguyễn Văn A  |
| 2 | A20-XXXXX   | Trần Thị B    |

## Đề bài được giao

Đề bài # ___ — [tên đề bài, vd: AI Support Copilot]

## Kết quả cuối

- 🎯🎯 [FILE TỔNG — Bảng kinh tế sản phẩm AI](./worksheet/04-FINAL-economics-sheet.md)
- 🎯 [Phần A — Mô hình chi phí](./worksheet/01-cost-model/3-FINAL-cost-model.md)
- 🎯 [Phần B + C — Định giá/Truy cập + Giá trị/ROI](./worksheet/02-pricing-value/3-FINAL-pricing-value-roi.md)
- 🎯 [Phần D — Kịch bản xấu + Quyết định](./worksheet/03-stress-test/3-FINAL-stress-test-verdict.md)

## Quyết định cuối

**[GO / CONDITIONAL / NO-GO]**

ROI cơ bản: ___:1
ROI kịch bản kết hợp xấu nhất: ___:1
```

### Các bước nộp

1. Tạo kho GitHub công khai theo cú pháp `Day27-MãNhóm`.
2. Đưa toàn bộ thư mục `worksheet/` lên kho theo đúng cấu trúc trên.
3. Tạo `README.md` ở gốc kho theo mẫu, điền mã học viên + họ tên đầy đủ + số đề bài + quyết định cuối.
4. Đảm bảo file TỔNG `04-FINAL-economics-sheet.md` có đầy đủ 4 Phần.
5. Một thành viên đại diện nộp đường dẫn kho vào LMS Ngày 27, kiểm tra đường dẫn mở được trước **23:59 hôm nay**.

---

## Quy trình làm bài

```text
Đọc lại bài giảng Ngày 27 (Cost-Capability-Speed Triangle, Monetization Triad,
   Value Metric Spectrum, kịch bản xấu)
   -> Đọc 00-worked-example.md (Đề bài #1 đã điền sẵn — biết bản CHỐT trông thế nào)
   -> Điền 00-context.md (đề bài được giao + 5 con số chính + nhà cung cấp dự định dùng)
   -> Bước 1: Mô hình chi phí (40 phút)
      -> Pha 1: Định nghĩa đơn vị AI làm việc + ước tính khối lượng (15')
      -> Pha 2: Tra giá nhà cung cấp + chi phí mỗi lần chạy (15')
      -> Pha 3: Chốt Phần A (10')
   -> Bước 2: Định giá/Truy cập + Giá trị/ROI (40 phút)
      -> Pha 1: Định vị trên ma trận Attribution × Autonomy (15')
      -> Pha 2: Chọn cách định giá + đơn vị tính tiền (10')
      -> Pha 3: Chốt Phần B + C — Giá trị mỗi tháng + ROI (15')
   -> Bước 3: Kịch bản xấu + Quyết định (40 phút)
      -> Pha 1: Bảng 5 kịch bản xấu (20')
      -> Pha 2: Bản nháp quyết định + điều kiện (10')
      -> Pha 3: Chốt Phần D (10')
   -> Gộp 4 Phần vào file TỔNG 04-FINAL-economics-sheet.md
   -> Rà soát bảng kiểm
   -> Nộp đường dẫn kho qua LMS
```

---

## Bước 1 — Mô hình chi phí (10:10–10:50, 40 phút)

Mục tiêu: định nghĩa đơn vị AI làm việc + tính chi phí AI mỗi tháng cho đề bài.

File chốt của Bước 1: `worksheet/01-cost-model/3-FINAL-cost-model.md` (= Phần A của Bảng kinh tế)

### Pha 1 — Đơn vị AI làm việc + khối lượng (15 phút)

Mỗi thành viên đề xuất một phương án đơn vị. Cặp chọn một, kiểm tra qua **3 câu hỏi**:

1. **Đếm được không?** — có thể đếm số lần AI chạy mà không tranh cãi.
2. **Có tốn token không?** — mỗi lần chạy = một lần gọi API thật, có chi phí.
3. **Người dùng có thấy giá trị không?** — một lần AI làm việc này có rút ngắn thời gian hoặc cải thiện chất lượng cho ai cụ thể không?

Sau đó tính khối lượng:

```text
Khối lượng mỗi ngày của nhóm thử nghiệm = (Người dùng pilot / Tổng đội) × Khối lượng mỗi ngày của toàn đội
Khối lượng mỗi tháng = Khối lượng mỗi ngày × 22 ngày làm việc
```

File làm việc của pha này: `worksheet/01-cost-model/1-usage-unit.md`

### Pha 2 — Tra giá nhà cung cấp (15 phút)

Nhóm tự tra giá, **không có giá cho sẵn**:

- Mở trang giá của nhà cung cấp AI (OpenAI / Anthropic / Google) → tìm $/1M token.
- Ước tính số token mỗi lần chạy (đầu vào + đầu ra) → tính chi phí mỗi lần chạy = (token vào × giá vào + token ra × giá ra) / 1M.
- Tra thêm chi phí công cụ phụ trợ (vector DB, monitoring), chi phí người kiểm tra lại, chi phí dựng ban đầu.

Quy tắc: **mỗi con số tiền phải có URL mở được**.

File làm việc: `worksheet/01-cost-model/2-cost-research.md`

### Pha 3 — Chốt Phần A (10 phút)

Gộp vào `3-FINAL-cost-model.md` với 8 mục con (A.1 Đơn vị AI làm việc → A.8 Đối chiếu ngân sách).

Công thức chi phí mỗi tháng:

```text
Chi phí mỗi tháng = (Khối lượng × Chi phí API mỗi lần) + Công cụ phụ trợ
                  + (Khối lượng × Chi phí người kiểm tra) + Chi phí dựng đầu chia đều
```

---

## Bước 2 — Định giá/Truy cập + Giá trị/ROI (10:50–11:30, 40 phút)

Mục tiêu: chốt cách định giá, tính giá trị mỗi tháng, tính ROI.

File chốt: `worksheet/02-pricing-value/3-FINAL-pricing-value-roi.md` (= Phần B + C)

### Pha 1 — Định vị Attribution × Autonomy (15 phút)

Đặt sản phẩm trên ma trận 2×2:

- **Autonomy** (mức độ tự chủ): AI tự làm xong (cao) hay chỉ hỗ trợ người (thấp)?
- **Attribution** (mức độ quy công): AI là nguyên nhân rõ ràng của kết quả (cao) hay khó tách công của AI khỏi công người (thấp)?

Ô nhóm rơi vào quyết định cách định giá tự nhiên:

```text
                Attribution thấp        Attribution cao
Autonomy thấp   Seat / Flat             Hybrid (Seat + Credits)
                (Grammarly)             (Cursor)
Autonomy cao    Usage-based             Outcome-based
                (OpenAI API)            (Intercom Fin)
```

File: `worksheet/02-pricing-value/1-attribution-autonomy.md`

### Pha 2 — Cách định giá + đơn vị tính tiền (10 phút)

Chọn 1 trong 4 cách định giá + đặt mức giá cụ thể + chọn đơn vị tính tiền (value metric) qua 3 câu hỏi kiểm tra.

Đánh giá rủi ro Usage Anxiety *(người dùng tự hạn chế xài AI vì sợ hóa đơn tăng)* nếu cách định giá có yếu tố theo lượng dùng.

File: `worksheet/02-pricing-value/2-pricing-model-choice.md`

### Pha 3 — Chốt giá trị mỗi tháng + ROI (15 phút)

Tính thời gian tiết kiệm THỰC TẾ (không dùng "gộp" thô):

```text
Thực tế = Gộp − Thời gian chờ AI − Thời gian người kiểm tra − Chuyển ngữ cảnh − Sửa lại
```

Công thức giá trị mỗi tháng:

```text
Gộp = Khối lượng × Thời gian tiết kiệm THỰC TẾ × (Lương theo giờ / 60)
Điều chỉnh = Gộp × Tỷ lệ sử dụng thực tế × Tỷ lệ đạt chất lượng
Giá trị ròng = Điều chỉnh − Chi phí sửa lại
```

ROI = Giá trị mỗi tháng / Chi phí mỗi tháng.

**Kiểm tra lại cho hợp lý**:

- Tỷ lệ sử dụng thực tế > 80% → cần dữ liệu cứng chứng minh.
- Tỷ lệ đạt chất lượng > 85% → cần kết quả thử nghiệm thật.
- Thời gian thực tế > 80% gộp → kiểm tra lại các khoản phụ phí ẩn.
- ROI > 20:1 → khả năng cao đang lạc quan quá.

---

## Bước 3 — Kịch bản xấu + Quyết định (11:30–12:10, 40 phút)

Mục tiêu: kiểm tra xem ROI có sống nổi qua 5 kịch bản xấu + một kịch bản kết hợp → chốt quyết định.

File chốt: `worksheet/03-stress-test/3-FINAL-stress-test-verdict.md` (= Phần D)

### Pha 1 — 5 kịch bản xấu (20 phút)

Mỗi kịch bản thay đổi đúng một biến:

| # | Kịch bản | Thay đổi |
|---|---|---|
| 1 | Cơ bản | Đối chứng — không thay đổi |
| 2 | Dùng nặng | Khối lượng × 2-3 (mẫu hành vi của power user) |
| 3 | Tỷ lệ dùng thấp | Tỷ lệ sử dụng còn 30-40% (kiểu pilot thất bại) |
| 4 | Chất lượng giảm | Chất lượng còn 50-60% (mô hình có vấn đề) |
| 5 | Nhà cung cấp đổi giá | Giá API × 2-3 (deprecate / đổi bảng giá) |

Kịch bản kết hợp xấu nhất = 2 kịch bản tệ nhất xảy ra cùng lúc.

File: `worksheet/03-stress-test/1-scenario-table.md`

### Pha 2 — Bản nháp quyết định (10 phút)

Áp tiêu chí:

| Tiêu chí | GO | CONDITIONAL | NO-GO |
|---|---|---|---|
| ROI cơ bản | > 3:1 | 1.5-3:1 | < 1.5:1 |
| Sống qua mấy/5 kịch bản | 4-5 | 2-3 | 0-1 |
| ROI kịch bản kết hợp xấu nhất | > 1.5:1 | 1-1.5:1 | < 1:1 |

CONDITIONAL là kết quả phổ biến nhất (chiếm 70%+ pilot AI). GO chỉ xảy ra khi ROI cơ bản > 3:1 VÀ sống qua 4/5 kịch bản VÀ kết hợp xấu nhất > 1.5:1.

File: `worksheet/03-stress-test/2-verdict-draft.md`

### Pha 3 — Chốt Phần D (10 phút)

Gộp vào file CHỐT với 8 mục con (D.1 Bảng kịch bản xấu → D.8 Những thay đổi cần làm nếu NO-GO).

Điều kiện cứng (nếu là CONDITIONAL): 3-5 điều kiện đo được + có mốc thời gian + có hành động cụ thể.

---

## Kho 10 đề bài (Challenge Brief Bank)

Mỗi cặp nhận một trong 10 đề bài. Chi tiết trong `challenge-brief-bank.md`.

| # | Đề bài | Ngành |
|---|---|---|
| 1 | AI Support Copilot | B2B SaaS hỗ trợ khách hàng (đề bài có lời giải đầy đủ) |
| 2 | AI Content Moderator | Nền tảng mạng xã hội — kiểm duyệt nội dung |
| 3 | AI Medical Triage Assistant | Khoa cấp cứu bệnh viện |
| 4 | AI Legal Contract Reviewer | Văn phòng luật M&A |
| 5 | AI Sales Email Generator | Sales B2B trong thương mại điện tử |
| 6 | AI Code Review Assistant | Đội kỹ thuật fintech |
| 7 | AI Inventory Forecaster | Chuỗi bán lẻ — quản lý kho |
| 8 | AI Student Essay Grader | Chấm bài viết bậc đại học |
| 9 | AI Insurance Claim Processor | Bảo hiểm phi nhân thọ |
| 10 | AI Real Estate Listing Generator | Đại lý bất động sản |

---

## Tài liệu trong thư mục này

| File / Thư mục | Dùng để làm gì |
|---|---|
| `challenge-brief-bank.md` | Kho 10 đề bài (mỗi cặp một đề bài) |
| `glossary.md` | Bảng thuật ngữ Ngày 27 (chi phí, định giá, giá trị, kịch bản xấu, quyết định) |
| `worksheet/00-context.md` | Điền ngữ cảnh nhóm + đề bài được giao — làm một lần đầu buổi |
| `worksheet/00-worked-example.md` | Bản Bảng kinh tế đã điền đầy đủ cho Đề bài #1 — đọc trước Lab để biết mức chi tiết được kỳ vọng |
| `worksheet/01-cost-model/` | Bước 1 — 3 file (1-usage-unit, 2-cost-research, 3-FINAL-cost-model) |
| `worksheet/02-pricing-value/` | Bước 2 — 3 file |
| `worksheet/03-stress-test/` | Bước 3 — 3 file |
| `worksheet/04-FINAL-economics-sheet.md` | 🎯🎯 File TỔNG — gộp 4 Phần |
| `prompts/` | 10 câu lệnh AI tham khảo cho từng pha |

---

## Bảng câu lệnh AI tham khảo

| Câu lệnh tham khảo | Dùng khi nào | Lưu kết quả vào |
|---|---|---|
| `prompts/01-define-usage-unit.md` | Định nghĩa đơn vị AI làm việc (Bước 1 Pha 1) | `01-cost-model/1-usage-unit.md` |
| `prompts/02-cost-formula.md` | Tra giá + tính chi phí mỗi lần chạy (Bước 1 Pha 2) | `01-cost-model/2-cost-research.md` |
| `prompts/03-attribution-autonomy.md` | Định vị trên ma trận 2×2 (Bước 2 Pha 1) | `02-pricing-value/1-attribution-autonomy.md` |
| `prompts/04-pricing-model-choice.md` | Chốt cách định giá (Bước 2 Pha 2) | `02-pricing-value/2-pricing-model-choice.md` |
| `prompts/05-value-formula.md` | Tính giá trị mỗi tháng (Bước 2 Pha 3) | `02-pricing-value/3-FINAL` Phần C |
| `prompts/06-roi-analysis.md` | Tính ROI + phân tích nhạy cảm (Bước 2 Pha 3) | `02-pricing-value/3-FINAL` Phần C.6 + C.7 |
| `prompts/07-stress-scenario.md` | Dựng 5 kịch bản xấu (Bước 3 Pha 1) | `03-stress-test/1-scenario-table.md` |
| `prompts/08-verdict-writing.md` | Viết quyết định + điều kiện (Bước 3 Pha 2) | `03-stress-test/2-verdict-draft.md` |
| `prompts/09-cross-brief-comparison.md` | So sánh kết quả với cặp khác đề bài (sau Lab) | `04-FINAL-economics-sheet.md` (phần So sánh) |
| `prompts/10-presentation-prep.md` | Chuẩn bị 6 phút trình bày (cuối Lab) | Slide / script riêng |

---

## Cách dùng câu lệnh AI tham khảo

1. Mở Claude / ChatGPT / Gemini / Perplexity tùy bước.
2. Dán toàn bộ `worksheet/00-context.md` + đề bài (từ `challenge-brief-bank.md`) vào đầu cuộc trò chuyện.
3. Dán thêm các file đã làm ở pha trước (vd: `1-usage-unit.md` cho câu lệnh 02; `3-FINAL-cost-model.md` cho câu lệnh 05).
4. Chọn câu lệnh tham khảo phù hợp từ thư mục `prompts/`, rồi chỉnh lại cho khớp ngữ cảnh nhóm.
5. AI tạo bản nháp.
6. Nhóm đọc lại, sửa, kiểm chứng từng số, rồi lưu vào đúng file bài tập.

AI chỉ hỗ trợ dựng bản nháp. Nhóm vẫn tự chịu trách nhiệm các phần sau:

- Bấm vào URL trang giá để kiểm tra số tiền.
- Giải thích vì sao chọn từng tỷ lệ phần trăm (tỷ lệ sử dụng thực tế, tỷ lệ đạt chất lượng).
- Kiểm tra lại cho hợp lý phần ROI (>20:1 hay <1:1 = phải rà lại).
- Bảo vệ quyết định cuối trong phần hỏi đáp.

### Những lưu ý quan trọng khi dùng AI

- **Đừng để AI bịa giá**: AI có thể bịa giá cho mô hình mới hoặc mô hình đã ngừng phát hành. Luôn bấm vào trang giá thật.
- **Đừng để AI viết quyết định cuối**: AI tổng hợp tốt nhưng không có quan điểm — nhóm phải tự ra quyết định và tự bảo vệ.
- **Đừng để AI lạc quan quá**: AI có xu hướng đặt tỷ lệ sử dụng thực tế > 80% và chất lượng > 90%. Đối chiếu lại với mốc tham chiếu thực tế.

---

## Bảng kiểm trước khi nộp

### Bước 1 — Mô hình chi phí

- [ ] Đơn vị AI làm việc qua được 3 câu kiểm tra (đếm, tốn token, có giá trị).
- [ ] Khối lượng mỗi ngày của nhóm thử nghiệm tính theo công thức (pilot/tổng × khối lượng toàn đội).
- [ ] Có URL trang giá cho nhà cung cấp + mô hình cụ thể.
- [ ] Chi phí mỗi lần chạy tính theo công thức token (không phải "ước lượng").
- [ ] Đã tính chi phí người kiểm tra nếu đề bài có ràng buộc.
- [ ] Chi phí dựng đầu chia đều theo số tháng pilot.
- [ ] Công thức chi phí mỗi tháng có 4 thành phần cộng lại = tổng.
- [ ] Đã đối chiếu chi phí với ngân sách trong đề bài (trường 8).

### Bước 2 — Định giá/Truy cập + Giá trị/ROI

- [ ] Định vị trên ma trận Attribution × Autonomy có lý do giải thích.
- [ ] Cách định giá rõ (1 trong 4) + có mức giá cụ thể.
- [ ] Đơn vị tính tiền qua được 3 câu kiểm tra.
- [ ] Sản phẩm thực tế tương đương có URL.
- [ ] Đã đánh giá Usage Anxiety Thấp / Vừa / Cao.
- [ ] Thời gian tiết kiệm thực tế = Gộp − chờ − kiểm tra − chuyển ngữ cảnh − sửa lại.
- [ ] Tỷ lệ sử dụng thực tế + tỷ lệ đạt chất lượng có lý do.
- [ ] ROI là một con số cụ thể (___ : 1).
- [ ] Đã kiểm tra lại cho hợp lý (không > 20:1 hoặc < 1:1 mà thiếu lý do).

### Bước 3 — Kịch bản xấu + Quyết định

- [ ] 5 kịch bản đều có chi phí + giá trị + ROI mới + tình trạng (sống / không).
- [ ] Kịch bản kết hợp xấu nhất dùng đúng 2 kịch bản tệ nhất.
- [ ] Đã tính điểm hòa vốn theo tỷ lệ sử dụng + chất lượng (không bắt buộc nhưng cộng điểm).
- [ ] Đã CHỌN rõ quyết định (GO / CONDITIONAL / NO-GO).
- [ ] Nếu CONDITIONAL: có 3-5 điều kiện kèm cách đo + mốc thời gian + hành động.
- [ ] Có 3-5 chỉ số giám sát kèm ngưỡng cứng.
- [ ] Có ngưỡng dừng/đổi hướng cụ thể (số + thời gian + hành động).

### File TỔNG

- [ ] Có 1-2 câu tóm tắt cho người mua đọc trước.
- [ ] Phần A đủ 8 mục con.
- [ ] Phần B đủ 4 mục con.
- [ ] Phần C đủ 7 mục con.
- [ ] Phần D đủ 8 mục con.
- [ ] Có 3 bài học nối ngang giữa các Phần.
- [ ] Có so sánh với Ngày 26 (nếu có điểm chung).

### Nộp

- [ ] Kho GitHub công khai, tên đúng cú pháp `Day27-MãNhóm`, mở được.
- [ ] README đầu kho có bảng mã học viên + họ tên đầy đủ + số đề bài + quyết định cuối.
- [ ] File TỔNG `04-FINAL-economics-sheet.md` có thể bấm thẳng từ README.
- [ ] Đã nộp đường dẫn kho qua LMS trước **23:59**.

---

## Những lỗi hay mắc

| Đừng làm | Nên làm |
|---|---|
| Bỏ qua `00-context.md` | Điền ngữ cảnh + số đề bài + 5 con số chính trước khi vào Lab |
| Chỉ nộp file TỔNG | Giữ cả 9 file trung gian (3 file × 3 Bước) để người chấm thấy quá trình suy luận |
| Đơn vị AI làm việc kiểu "AI hỗ trợ X" | Cụ thể "1 ___" qua được 3 câu kiểm tra |
| Tính theo khối lượng toàn đội | Dùng khối lượng nhóm thử nghiệm (pilot/tổng × toàn đội × 22) |
| Chi phí mỗi lần chạy = $0 (quên tra giá) | Bấm vào URL trang giá, tính theo số token |
| Chỉ tính chi phí API, quên người kiểm tra | Chi phí người kiểm tra thường chiếm phần lớn (50-90%) |
| Chi phí dựng đầu = $0 | Luôn có (tích hợp + viết câu lệnh + đào tạo) |
| Tỷ lệ sử dụng 100% / chất lượng 95% | Thực tế: 50-80% sử dụng thực tế, 60-85% chất lượng |
| Tính theo thời gian tiết kiệm gộp (chưa trừ phụ phí) | Thực tế = Gộp − chờ − kiểm tra − chuyển ngữ cảnh − sửa lại |
| ROI > 20:1 mà không đặt câu hỏi | Rà lại giả định, tính lại theo hướng dè dặt |
| ROI < 1:1 thì NO-GO ngay | Tìm đòn bẩy trước (mô hình rẻ hơn, mở rộng nhóm pilot) |
| Quyết định GO chắc chắn | CONDITIONAL kèm điều kiện cứng dễ bảo vệ hơn |
| Điều kiện chung chung "theo dõi tỷ lệ sử dụng" | Cụ thể: "Tỷ lệ sử dụng ≥ 60% tháng 1, kiểm tra hàng tuần" |
| Kịch bản kết hợp xấu = 1 kịch bản | Kết hợp = 2 kịch bản cùng lúc |
| Bỏ ngưỡng dừng | Ngưỡng = số + thời gian + hành động cụ thể |
| Đặt tên kho `Day-27-team-final` | Đúng cú pháp `Day27-MãNhóm` (vd: `Day27-G007`) |

---

## Liên kết với Ngày 26 và Ngày 28

Ngày 27 là cây cầu nối giữa Ngày 26 (Chiến lược) và Ngày 28 (Bảo vệ trước hội đồng):

- **Đầu vào từ Ngày 26**: Bảng chứng cứ (4 Lens + Spark/Loop/System) — biết sản phẩm chiến lược nào sống nổi.
- **Sản phẩm Ngày 27**: Bảng kinh tế (Chi phí + Định giá + Giá trị + Kịch bản xấu + Quyết định) — biết sản phẩm nào sống nổi **về mặt kinh tế**.
- **Bảo vệ Ngày 28**: Gộp Ngày 26 + Ngày 27, trình bày trước hội đồng CTO/CFO/mentor, bảo vệ bằng cả lý lẽ chiến lược lẫn lý lẽ kinh tế.

Trước khi kết thúc Ngày 27, nhóm nên chuẩn bị thêm cho Ngày 28:

- Đọc kỹ lại quyết định + điều kiện — người mua sẽ đào sâu.
- Lường trước 5 câu hỏi khó nhất (xem `prompts/10-presentation-prep.md`).
- Slide chuẩn bị riêng (PDF / Google Slides) — không nằm trong worksheet.

Đường dẫn cuối: Bảng chứng cứ Ngày 26 → **Bảng kinh tế Ngày 27** → Gói trình bày Ngày 28.

---

## Lời khuyên cuối

1. **Mỗi con số phải có công thức**. Đây là kỷ luật cốt lõi của Ngày 27.
2. **CONDITIONAL không phải thất bại**. CONDITIONAL kèm điều kiện cứng vẫn mạnh hơn GO chắc nịch mà không qua kịch bản xấu.
3. **Luôn nhớ góc nhìn người mua**. Mỗi quyết định tự hỏi: CTO/CFO có bảo vệ được không?
4. **Chỉnh câu lệnh AI 1-2 lượt** trước khi dán vào worksheet. Bản nháp đầu thường lạc quan quá.
5. **Glossary là bạn**. Khi gặp thuật ngữ → mở `glossary.md` trước khi hỏi AI.

Chúc nhóm có một ngày Build trọn vẹn. Mai gặp ở Ngày 28 Bảo vệ — mang theo cả Ngày 26 và Ngày 27.
