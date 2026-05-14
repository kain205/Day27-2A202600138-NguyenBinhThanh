# Câu lệnh AI 4 — Chốt mô hình định giá + đơn vị tính tiền

**Dùng khi**: Bước 2 Lab, sau khi định vị trên ma trận — nhóm cần chốt 1 trong 4 mô hình (theo người dùng / theo lượng / theo kết quả / kết hợp) và chốt đơn vị khách trả tiền cho.

**Công cụ gợi ý**: Claude, ChatGPT.

**Lưu kết quả vào**: `worksheet/02-pricing-value/2-pricing-model-choice.md` + phần B trong `3-FINAL-pricing-value-roi.md`.

**Thời gian**: 10–15 phút.

---

## Trước khi vào câu lệnh — 5 câu nhóm tự trả lời

Chọn mô hình định giá không phải vì "đang là xu hướng" — phải vì 4 yếu tố hợp lại: vị trí trên ma trận, người mua, cấu trúc chi phí, và thói quen người dùng. Trả lời 5 câu này trước.

1. Ô đã chốt trên ma trận (từ câu lệnh 3): tự chủ ___ + gắn-rõ ___.
2. Người mua trong đề bài là ai (đọc trường 6 — quyết định cần ra)? Giám đốc kỹ thuật, phó tổng kinh doanh, trưởng phòng, đối tác điều hành?
3. Chi phí mỗi lần chạy đã tính ở Cost Model: $___. Nếu tính theo lượng, giá bán phải cao hơn chi phí + biên lợi nhuận.
4. Người dùng cuối có thể tự "ghìm" mình lại không (vd: nhân viên "ngại bấm AI" vì sợ tốn tiền)? Đây là rủi ro lo-lắng-khi-dùng.
5. Người mua mong muốn chi phí ổn định (predictable) hay biến động theo lượng dùng (pay-as-you-grow)?

---

## Câu lệnh chính (dán sau kết quả câu lệnh 3)

```text
Bạn là chuyên gia chiến lược định giá cho sản phẩm AI.
Dựa trên bối cảnh ở trên (đề bài + Cost Model + ô trên ma trận
Attribution × Autonomy), giúp nhóm tôi CHỐT mô hình định giá và đơn vị
khách trả tiền cho.

Phần 1 — Chốt mô hình định giá:
4 mô hình chính:
- Theo người dùng (Seat / Flat): $X/người/tháng cố định.
- Theo lượng (Usage-based): $X / đơn vị lượng dùng.
- Theo kết quả (Outcome-based): $X / kết quả thực tế.
- Kết hợp (Hybrid): phần cố định + phần biến đổi, hoặc theo bậc kết quả.

Chọn 1 mô hình + giải thích vì sao (so với 3 mô hình còn lại):
- Lý do vị trí: mô hình nào tự nhiên cho ô của nhóm tôi?
- Lý do người mua: người mua sẽ duyệt mô hình nào dễ hơn?
- Lý do cấu trúc chi phí: chi phí mỗi lần chạy cao hay thấp → mô hình
  nào trụ được?

Đề xuất giá cụ thể, vd:
- "$25/người/tháng + 1.000 tín dụng/người, $0,05/tín dụng vượt"
- "$0,05/lần tạo nháp, không tối thiểu"
- "$1,50/lần xử lý xong, tính theo tháng"

Quy tắc cứng: nếu định giá theo lượng hoặc kết quả → GIÁ BÁN phải lớn
hơn chi phí mỗi lần chạy ít nhất 2–3 lần (để có biên lợi nhuận khoảng
70–80% — chuẩn SaaS B2B).

Phần 2 — Chốt đơn vị khách trả tiền cho:
Đơn vị này = thứ khách hàng đếm và bị tính tiền theo.

Đề xuất 3 phương án, mỗi phương án qua 3 câu kiểm tra:
- Khách đo được đơn vị này không (countable)?
- Người mua thấy đơn vị này có ý nghĩa không (meaningful)?
- Đơn vị có gắn với giá trị AI tạo ra không (tied to AI)?

Chọn 1 + lý do.

Phần 3 — Người mua và lý do mua hôm nay:
- Người mua là ai (vai trò)?
- Hiện giờ họ đang chi ngân sách gì cho vấn đề này (chi phí thay thế)?
- Giá đề xuất so với chi phí thay thế (vd: thuê thêm người, thuê ngoài)?
- Lý do người mua quyết định mua HÔM NAY là gì?

Phần 4 — Rủi ro lo-lắng-khi-dùng:
Nếu giá có phần biến đổi theo lượng:
- Người dùng cuối có thấy chi phí mỗi lần dùng không?
- Người dùng có thể tự "ghìm" để tránh tốn tiền không?
- Mức rủi ro: Thấp / Trung bình / Cao.
- Cách giảm rủi ro: gói số lượt trong bậc, ẩn chi phí cá nhân, cho hạn
  mức khám phá miễn phí.

Phần 5 — Phân tích nhạy cảm:
- Nếu giảm giá 30% (đối thủ rẻ hơn) → biên lợi nhuận còn bao nhiêu?
- Nếu chi phí mỗi lần chạy tăng 50% (nhà cung cấp đổi giá) → biên còn?
- Nếu tỷ lệ sử dụng thực tế chỉ 50% → doanh thu mỗi đợt thử nghiệm bao
  nhiêu?

Yêu cầu trình bày:
- Viết tiếng Việt thoát nghĩa.
- Mỗi đề xuất có lý do cụ thể (không "cảm thấy").

Yêu cầu phản biện:
- Mô hình định giá có mâu thuẫn với kỳ vọng người mua không?
- Đơn vị tính tiền có bảo vệ được trong buổi bán hàng và buổi nhận
  bàn giao với khách không?
- Có mô hình thay thế nào cũng hợp lý, lý do không chọn?
```

---

## Iterate — đẩy AI sâu hơn khi bản nháp chưa đủ

### Khi 2 mô hình định giá đều hợp lý cho đề bài

```text
2 mô hình đều hợp lý cho đề bài của tôi:
- Lựa chọn A: (vd: $25/người không giới hạn dùng)
- Lựa chọn B: (vd: $1,50/kết quả)

So sánh chi tiết:

| Góc nhìn | Lựa chọn A (Theo người) | Lựa chọn B (Theo kết quả) |
|---|---|---|
| Chi phí dự đoán được cho người mua | Có | Không (biến đổi) |
| Bảo vệ ROI (AI tạo giá trị rõ) | Khó tách | Mỗi kết quả rõ |
| Rủi ro người dùng ghìm tay vì sợ tốn | Thấp | Trung bình |
| Bán có phức tạp không | Đơn giản | Phức tạp (phải giáo dục) |
| Biên khi quy mô tăng | Tăng theo số người | Tăng theo số kết quả |
| Giám đốc kỹ thuật duyệt | Dễ (ổn định) | Khó (biến đổi) |
| Giám đốc tài chính duyệt | "Gói gọn trong người dùng" | "Mỗi kết quả rõ ràng" |

Đề xuất: Lựa chọn ___ vì ___.

Hoặc xem mô hình kết hợp: $20/người (cố định) + $0,50/kết quả khi vượt
100 kết quả/tháng. Kết hợp cân được giữa ổn định và bảo vệ ROI.
```

### Khi giá đề xuất không cao hơn chi phí đủ nhiều

```text
Giá nhóm tôi đề xuất = $0,05/lần, nhưng chi phí mỗi lần chạy = $0,04.

Biên lợi nhuận = 25% — không đủ cho SaaS B2B (thường cần ≥ 70–80%).

Các lựa chọn:
A. Tăng giá lên $0,15/lần (3× chi phí) → biên 73%. Rủi ro: khách thấy đắt?
B. Giữ $0,05/lần nhưng đặt phí tối thiểu $500/tháng (gói 10.000 lần) →
   giá thực tế trung bình ~$0,07/lần.
C. Đổi sang tính theo người ($25/người) cover chi phí + biên.

Tính từng lựa chọn:
- A: doanh thu = khối lượng × $0,15 = $___. Biên = $___. Chấp nhận được?
- B: doanh thu = $500 × số người = $___. Biên thực tế?
- C: doanh thu = số người × $25 = $___. Bảo vệ được so với chi phí?

Đề xuất lựa chọn nào bảo vệ được trong buổi nhận bàn giao với khách?
```

### Khi muốn căn chỉnh với người mua

```text
Người mua trong đề bài = ___ (vai trò).

Giá nhóm tôi đề xuất: ___.

Người mua thường lo lắng:
- Giám đốc kỹ thuật: "Chi phí có tăng theo lượng không? Biến đổi = khó
  lập ngân sách."
- Giám đốc tài chính: "ROI có bảo vệ được không? Có gắn với chỉ số kinh
  doanh không?"
- Phó tổng vận hành: "Tỷ lệ sử dụng có tăng theo thiết kế không? Có gây
  lo-lắng-khi-dùng không?"
- Đối tác điều hành (firm luật): "Tính theo từng vụ được không? Có thể
  thu lại từ khách hàng cuối?"

Giá đề xuất có giải quyết được lo lắng của người mua không?
Nếu KHÔNG → sửa lại giá để khớp hơn.

Vd: đề bài #4 (Luật) — đối tác điều hành thích tính theo kết quả (mỗi
hợp đồng) vì có thể thu lại từ khách hàng trong vụ M&A. Tính theo người
khó chuyển sang khách cuối.
```

---

## Trước khi dán kết quả vào worksheet — nhóm tự rà soát

- Mô hình định giá có rõ ràng (1 trong 4 nhóm + giá cụ thể)?
- Đơn vị tính tiền có qua được 3 câu kiểm tra?
- Người mua có dễ duyệt giá này không?
- Biên có khỏe (giá ≥ chi phí × 2–3)?
- Nếu có phần biến đổi theo lượng → đã có cách giảm rủi ro lo-lắng-khi-dùng chưa?

---

## Câu hỏi mở rộng (chỉ làm khi còn thời gian)

```text
Sau khi chốt giá, nhìn 3 góc chiến lược:

1. Giá thay đổi theo giai đoạn:
   - Thử nghiệm: giảm giá 50% để có tỷ lệ sử dụng.
   - Sản xuất chính thức: giá đầy đủ.
   - Trưởng thành: nếu đã có ưu thế thị trường → có thể tăng giá?

2. Đối thủ rẻ hơn 50% — phản ứng thế nào?
   - Theo: mất biên lợi nhuận.
   - Khác biệt hoá: nhấn chất lượng / tích hợp → giữ giá.
   - Đóng gói thêm: thêm tính năng để biện minh mức cao.

3. Hành trình người mua: từ biết đến → thử → mua, giá đóng vai trò gì ở
   mỗi giai đoạn?
   - Dùng thử miễn phí (14 ngày, 100 lần)?
   - Mức miễn phí vĩnh viễn (10 lần/tháng)?
   - Tự đăng ký hay đội bán hàng tiếp xúc? Giá có công khai trên trang web?

3 câu này giúp đề bài có chiến lược định giá đầy đủ, không chỉ "1 con số".
```
