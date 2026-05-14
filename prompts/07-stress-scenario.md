# Câu lệnh AI 7 — Dựng 5 kịch bản nén thử + kịch bản tệ nhất

**Dùng khi**: Bước 3 Lab, sau khi đã có Cost + Value + ROI cơ bản — nhóm cần nén thử 5 kịch bản (cơ bản, dùng nặng, tỷ lệ sử dụng thấp, chất lượng kém, nhà cung cấp đổi giá) và kịch bản tệ nhất khi 2 cùng xảy ra.

**Công cụ gợi ý**: Claude, ChatGPT.

**Lưu kết quả vào**: `worksheet/03-stress-test/1-scenario-table.md` + phần D.1 và D.2 trong `3-FINAL-stress-test-verdict.md`.

**Thời gian**: 20 phút.

---

## Trước khi vào câu lệnh — 5 câu nhóm tự trả lời

Nén thử (stress test) khác phân tích nhạy cảm. Nhạy cảm = đổi 1 biến nhỏ. Nén thử = đổi 1 biến MẠNH (2–3 lần, hoặc giảm 30–50%) để mô phỏng "ngày xấu". Trả lời 5 câu trước để có khung.

1. Kịch bản cơ bản: Chi phí $___, Giá trị $___, ROI ___:1.
2. Các biến gốc: tỷ lệ sử dụng ___%, chất lượng ___%, chi phí mỗi lần chạy $___, khối lượng ___ việc/tháng.
3. Từ phân tích nhạy cảm (câu lệnh 6): biến nào nhạy nhất với ROI?
4. Đọc trường 9 đề bài (ranh giới rủi ro): rủi ro chính trong đề bài là gì?
5. Có ví dụ ngành tương tự đã từng gặp cú sốc nào không (Replit biên âm, Salesforce 3 lần đổi giá)?

---

## Câu lệnh chính (dán sau kết quả Cost + Value + ROI)

```text
Bạn là chuyên gia quản trị rủi ro cho sản phẩm AI.
Dựa trên bối cảnh ở trên (đề bài + ROI cơ bản), giúp nhóm tôi dựng 5
KỊCH BẢN NÉN THỬ + kịch bản tệ nhất khi 2 cùng xảy ra.

Quy tắc chung: mỗi kịch bản chỉ thay đổi 1 biến (giữ 7 biến khác nguyên).
Kịch bản tệ nhất = 2 kịch bản xảy ra đồng thời.

Phần 1 — Kịch bản 1 (Cơ bản — điểm so chiếu):
Chỉ xác nhận lại số. Không đổi gì.

Phần 2 — Kịch bản 2 (Dùng nặng):
Mô hình "người dùng quyền lực": 20% người dùng dùng 80% lượng.

- Hệ số dùng nặng hợp lý cho đề bài: × ___ (2× / 3× / 5×).
- Lý do: (vd: nhân viên dùng AI cho mọi ticket kể cả việc dễ; nhân viên
  kinh doanh dùng AI cao vì tiết kiệm thời gian).

Tính lại:
- Khối lượng mới: ___ × ___ = ___ việc.
- Chi phí mới — từng phần chạy thế nào theo khối lượng?
  - API: tăng tuyến tính.
  - Công cụ: thường cố định (vector DB, giám sát).
  - Người kiểm tra: tăng tuyến tính.
  - Triển khai: cố định (đã rải đều).
- Giá trị mới: tăng tuyến tính (giá trị/việc × khối lượng).
- ROI mới = Giá trị mới / Chi phí mới.

Nhận xét: dùng nặng thử xem chi phí có "bùng" nhanh hơn giá trị không.
- Nếu cả 2 cùng tăng tuyến tính → ROI gốc ≈ ROI dùng nặng. Đơn vị kinh
  tế ổn.
- Nếu chi phí có "nhảy bậc" (vượt bậc doanh nghiệp, gói miễn phí hết) →
  ROI sụp.
- Ví dụ thực: Replit biên âm vì 20% người dùng cực kỳ tích cực, chi phí
  vượt doanh thu.

Phần 3 — Kịch bản 3 (Tỷ lệ sử dụng thấp):
Thử nghiệm không có ai dùng.

- Tỷ lệ sử dụng mới: ___% (so với gốc ___%).
- Lý do: (vd: giao diện khó / đào tạo thiếu / người dùng phản kháng /
  không có thưởng).

Tính lại:
- Giá trị mới: thô × tỷ lệ mới × chất lượng.
- Chi phí: GIỮ NGUYÊN (cơ sở hạ tầng cố định, không co lại khi ít dùng).
- ROI mới = Giá trị mới / Chi phí gốc.

Nhận xét: tỷ lệ sử dụng thấp thường đau nhất, vì chi phí cố định nhưng
giá trị giảm tuyến tính với tỷ lệ sử dụng.

Phần 4 — Kịch bản 4 (Chất lượng kém):
AI cho ra kết quả kém hơn dự đoán.

- Chất lượng mới: ___% (so với gốc ___%).
- Lý do: (vd: trường hợp đặc biệt nhiều / tài liệu nội bộ cũ / ngành
  hẹp / chưa kịp tinh chỉnh).

Tính lại:
- Chi phí làm lại tăng: + $___/tháng (thời gian sửa kết quả tệ).
- Giá trị mới: thô × tỷ lệ × chất lượng mới − chi phí làm lại.
- Chi phí có thể tăng nhẹ (thử lại nhiều lần).
- ROI mới?

Phần 5 — Kịch bản 5 (Nhà cung cấp đổi giá):
Nhà cung cấp tăng giá hoặc ngừng mô hình.

- Hệ số sốc: × ___ (2× / 3×).
- Lý do: (vd: Anthropic ngừng Claude 3.5 → buộc dùng Claude 4 đắt hơn 60%;
  Salesforce đổi giá AI 3 lần / 18 tháng).

Tính lại:
- Chi phí API mới: API gốc × hệ số.
- Công cụ + kiểm tra + triển khai: giữ nguyên.
- Chi phí tổng mới?
- Giá trị: giữ nguyên (chi phí tăng không làm giá trị đổi ngay).
- ROI mới?

Nhận xét: thử xem có phụ thuộc "đất thuê" (rented land) không.
- Nếu chi phí API chỉ chiếm < 10% → sốc 2× chỉ tăng tổng < 10%. Vững.
- Nếu chi phí API chiếm > 50% → sốc 2× làm tổng × 1,5. Rủi ro.

Phần 6 — Kịch bản tệ nhất khi 2 cùng xảy ra:
Chọn 2 kịch bản tệ nhất trong 4 (từ phần 2 đến 5).

Áp 2 thay đổi cùng lúc:
- Thay đổi 1: ___
- Thay đổi 2: ___

Tính:
- Chi phí kết hợp: áp cả 2 thay đổi vào chi phí.
- Giá trị kết hợp: áp cả 2 thay đổi vào giá trị.
- ROI kết hợp: ___:1.

Diễn giải:

| ROI kết hợp | Xu hướng verdict |
|---|---|
| > 3:1 | Vững |
| 1,5–3:1 | Sống được |
| 1–1,5:1 | Hoà vốn, cần điều kiện giảm thiểu |
| 0,5–1:1 | Rủi ro, cần thiết kế lại |
| < 0,5:1 | Cấp thiết, NO-GO |

Yêu cầu trình bày:
- Mỗi kịch bản có chi phí + giá trị + ROI mới cụ thể.
- Mỗi kịch bản có lý do sốc (không "sốc ngẫu nhiên").
- Viết tiếng Việt thoát nghĩa.

Yêu cầu phản biện:
- Hệ số có thực tế không (2–3× phổ biến, > 5× hiếm)?
- Kịch bản kết hợp có chọn đúng 2 tệ nhất, có lý do không?
- Có kịch bản nào ROI MẠNH hơn cơ bản (ngược trực giác) không?
```

---

## Iterate — đẩy AI sâu hơn khi bản nháp chưa đủ

### Khi tất cả kịch bản đều > 3:1 (có vẻ quá vững)

```text
5 kịch bản của tôi đều có ROI > 3:1 — có vẻ kinh tế quá vững.

Kiểm tra lại:
1. Dùng nặng × 3 mà ROI vẫn > 3? Chi phí có "nhảy bậc" nào bị bỏ qua không?
2. Tỷ lệ sử dụng 30% mà ROI vẫn > 3? Có phần chi phí nào tự co lại không
   nên — nhưng chi phí cố định (triển khai, công cụ) thì không.
3. Chất lượng 50% mà ROI vẫn > 3? Đã tính chi phí làm lại (thường 0,5–2
   phút × tỷ lệ kém) chưa?
4. Nhà cung cấp × 2 mà ROI vẫn > 3? API chiếm bao nhiêu % tổng chi phí?

Nếu sau kiểm tra vẫn vững → ROI cơ bản đẹp quá (> 10:1). Cần kiểm tra
lại cơ bản.

Hoặc thử sốc mạnh hơn:
- Dùng nặng × 5 (cực đoan).
- Tỷ lệ sử dụng 20% (thử nghiệm gần như thất bại).
- Chất lượng 40% (mô hình sụp).
- Nhà cung cấp × 4 (ngừng hoàn toàn + đổi).

Kịch bản kết hợp ở mức cực đoan này — vẫn > 1:1 không?
```

### Khi một kịch bản có lý do mơ hồ

```text
Kịch bản 4 (Chất lượng kém) bạn đề xuất chất lượng = 60% — vì sao 60%
chính xác?

Cần lý do CỤ THỂ:
- Tài liệu nội bộ cũ 30% → nháp dựa trên thông tin sai 30% → chất lượng
  rơi về 60–65%.
- Ngành rất hẹp (luật M&A chuyên ngành) → mô hình chung không cover →
  chất lượng 50–65%.
- Chưa tinh chỉnh xong trong thử nghiệm 90 ngày → chất lượng 60–70%
  (chưa ổn định).
- Dữ liệu thử nghiệm hiện tại chỉ 75% → bi quan = giảm 10 điểm → 65%.

Chọn 1 lý do thực tế nhất. Mức giảm phụ thuộc nguyên nhân:
- Tài liệu: giảm ít, vì tìm tài liệu vẫn cover một phần.
- Ngành hẹp: giảm trung bình.
- Chưa tinh chỉnh: giảm lớn.

Đề xuất: chọn nguyên nhân sát với đề bài nhất + định ngưỡng giảm tương ứng.
```

---

## Trước khi dán kết quả vào worksheet — nhóm tự rà soát

- Đủ 5 kịch bản + 1 kết hợp tệ nhất chưa?
- Hệ số có thực tế không (2–3× cho phần lớn, không > 5× tuỳ tiện)?
- Mỗi sốc có lý do gắn với đề bài, không nói chung chung?
- Kịch bản kết hợp chọn đúng 2 tệ nhất, không tuỳ tiện?
- Mỗi kịch bản có rút ra "đau nhất ở đâu, vì sao"?

---

## Câu hỏi mở rộng (chỉ làm khi còn thời gian)

```text
Sau khi nén thử, suy nghĩ 3 góc:

1. Hồi phục: nếu kịch bản tệ nhất xảy ra, mất bao lâu để hồi phục?
   - Tỷ lệ sử dụng hồi phục: 3–6 tháng đào tạo tích cực.
   - Chất lượng hồi phục: 1–2 tháng tinh chỉnh câu lệnh + cập nhật tài
     liệu.
   - Chi phí hồi phục: phụ thuộc nhà cung cấp, 0–12 tháng.

2. Chi phí giảm thiểu rủi ro:
   - Ký hợp đồng nhà cung cấp 1 năm: cộng thêm chi phí 10–20%?
   - Thiết lập mô hình dự phòng: $5–10K thêm.
   - Chương trình tăng tỷ lệ sử dụng: $X/quý.
   - Chi phí giảm thiểu có bảo vệ được so với rủi ro tránh được không?

3. Hiệu ứng dây chuyền:
   - Tỷ lệ sử dụng thấp → ít dữ liệu phản hồi → chất lượng không cải
     thiện → tỷ lệ sử dụng càng giảm.
   - Có rủi ro dây chuyền nào trong đề bài không?
   - Chỉ số nào để theo dõi và cắt sớm chuỗi này?

3 câu này chuẩn bị cho verdict CONDITIONAL với điều kiện chặt — người
mua sẽ hỏi.
```
