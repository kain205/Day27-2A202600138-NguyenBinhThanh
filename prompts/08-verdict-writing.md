# Câu lệnh AI 8 — Viết verdict GO / CONDITIONAL / NO-GO

**Dùng khi**: cuối Bước 3 Lab, sau khi đã có 5 kịch bản nén thử + kịch bản tệ nhất — nhóm cần chốt verdict và viết điều kiện / thay đổi cụ thể.

**Công cụ gợi ý**: Claude, ChatGPT.

**Lưu kết quả vào**: `worksheet/03-stress-test/2-verdict-draft.md` + phần D.4 đến D.8 trong `3-FINAL-stress-test-verdict.md`.

**Thời gian**: 15 phút.

---

## Trước khi vào câu lệnh — 5 câu nhóm tự trả lời

Nhiều nhóm hay chọn GO chỉ vì "GO nghe như thành công". Thật ra, CONDITIONAL với điều kiện rõ là verdict CHUYÊN NGHIỆP nhất — vì nó thừa nhận có rủi ro và đề xuất cách giảm thiểu. Trả lời 5 câu này trước.

1. ROI cơ bản: ___:1.
2. ROI kịch bản kết hợp tệ nhất: ___:1.
3. Số kịch bản qua được (X/5, X = số kịch bản có ROI > 1,5:1).
4. Người mua trong đề bài là ai (giám đốc kỹ thuật, phó tổng, trưởng phòng)?
5. Có nhóm đang nghiêng về GO chỉ vì cảm giác "muốn pilot thành công" không?

---

## Câu lệnh chính (dán sau kết quả 5 kịch bản)

```text
Bạn là cố vấn tài chính giúp viết verdict cho thử nghiệm AI.
Dựa trên bối cảnh ở trên (đề bài + chi phí + giá trị + ROI + 5 kịch bản
nén thử + kịch bản tệ nhất), giúp nhóm tôi:

1. Áp tiêu chí → chọn verdict (GO / CONDITIONAL / NO-GO).
2. Viết tuyên bố verdict có thể hành động được.
3. Liệt kê điều kiện / thay đổi cụ thể.

Phần 1 — Áp tiêu chí:

| Tiêu chí | GO | CONDITIONAL | NO-GO |
|---|---|---|---|
| ROI cơ bản | > 3:1 | 1–3:1 | < 1:1 |
| Qua được X/5 kịch bản | 4–5 | 2–3 | 0–1 |
| ROI kịch bản tệ nhất | > 1,5:1 | 0,5–1,5:1 | < 0,5:1 |

Áp cho nhóm tôi:
- ROI cơ bản: ___:1 → tầng ___
- Qua X/5: ___/5 → tầng ___
- ROI tệ nhất: ___:1 → tầng ___

Nếu 3 dòng cùng chỉ vào 1 verdict → rõ.
Nếu lệch (vd: cơ bản GO nhưng tệ nhất NO-GO) → nghiêng về CONDITIONAL với
điều kiện chặt.

VERDICT đề xuất: ___

Phần 2 — Tuyên bố verdict (3–4 câu):

Phải có:
- Verdict rõ (GO / CONDITIONAL / NO-GO).
- Số ROI cơ bản + ROI tệ nhất (bảo vệ được).
- 1 điều kiện hoặc thay đổi quan trọng (nếu CONDITIONAL / NO-GO).

Theo verdict:

GO:
"Tiến hành thử nghiệm như đã thiết kế. Đề bài #___ [tên]. ROI cơ bản
___:1, qua [X/5] kịch bản. Kịch bản tệ nhất [tên 2 kịch bản kết hợp]
cho ROI ___:1, trên ngưỡng 1,5:1. Tiến hành không cần điều kiện."

CONDITIONAL:
"CONDITIONAL GO. Đề bài #___ [tên]. ROI cơ bản ___:1, qua [X/5] kịch
bản. Kịch bản tệ nhất [tên] cho ROI ___:1 — biên mỏng. Thử nghiệm tiếp
tục với điều kiện: 1) ___ 2) ___ 3) ___. Cắt nếu: ___."

NO-GO:
"NO-GO ở phạm vi hiện tại. Đề bài #___ [tên]. ROI cơ bản ___:1 hoặc tệ
nhất ___:1. Cần thay đổi: 1) ___ 2) ___ 3) ___. Loại: [Tạm thời / Vĩnh viễn]."

Phần 3 — Điều kiện (nếu CONDITIONAL):

3–5 điều kiện cụ thể, mỗi điều kiện có 4 trường:
- Tên điều kiện
- Đo bằng chỉ số gì (cụ thể)
- Khi nào kiểm tra (vd: cuối tháng 1, hàng tuần)
- Làm gì nếu không đạt

Vd:
"1. Tỷ lệ sử dụng phải ≥ 60% trong tháng 1.
   - Chỉ số: số người dùng / tổng nhóm thử nghiệm mỗi tuần.
   - Thời gian: hàng tuần, đánh giá cuối tháng 1.
   - Nếu không đạt: tạm dừng thử nghiệm, rà giao diện + đào tạo."

Quy tắc cứng: điều kiện phải ĐO ĐƯỢC + CÓ MỐC THỜI GIAN. Không "sẽ cố
gắng tốt".

Phần 4 — Chỉ số theo dõi:

3–5 chỉ số theo dõi trong suốt thử nghiệm:
- Tên + tần suất + nguồn dữ liệu + ngưỡng.

Vd:
- Tỷ lệ sử dụng: hàng tuần từ log hệ thống, ngưỡng ≥ 60%.
- Chi phí mỗi lần chạy: hàng tuần từ hoá đơn, ngưỡng ≤ $0,01.
- Chất lượng: hàng tuần qua mẫu ngẫu nhiên 50 việc, ngưỡng ≥ 75%.
- Điểm hài lòng người dùng: hàng tháng qua khảo sát, NPS ≥ 30.

Phần 5 — Điều kiện dừng / xoay:

Cứng: nếu X xảy ra trong Y thời gian → dừng / xoay.

Vd:
"Điều kiện 1: Tỷ lệ sử dụng < 40% trong 30 ngày liên tiếp → tạm dừng."
"Điều kiện 2: Chi phí mỗi lần chạy > $0,05 trong 2 tuần → đổi sang mô
hình rẻ hơn."
"Điều kiện 3: Chất lượng < 60% trong 30 ngày → dừng + tinh chỉnh câu lệnh."

Phần 6 — Thay đổi (nếu NO-GO):

Nếu NO-GO, liệt kê 2–3 thay đổi để khả thi:
- Tên thay đổi + tác động dự kiến lên ROI.

Vd:
"Thay đổi 1: Đổi Claude 3.5 → GPT-4o-mini cho việc đơn giản → chi phí
giảm 80%, ROI 0,7 → 2,1."
"Thay đổi 2: Đàm phán lại ràng buộc 100% người kiểm tra → ROI 2,1 → 3,4."

Loại NO-GO: "Tạm thời (xem lại khi A, B)" hay "Vĩnh viễn (về cơ bản không
phù hợp)".

Yêu cầu trình bày:
- Tuyên bố verdict ngắn (3–4 câu), bảo vệ được.
- Điều kiện / chỉ số / điều kiện dừng cụ thể, đo được, có mốc.
- Viết tiếng Việt thoát nghĩa.

Yêu cầu phản biện:
- Verdict CONDITIONAL có điều kiện khả thi không (không phụ thuộc phép
  màu)?
- Verdict GO có kiểm tra kịch bản cơ bản có phóng đại không?
- Verdict NO-GO có thực sự "vĩnh viễn" hay chỉ "tạm thời"?
```

---

## Iterate — đẩy AI sâu hơn khi bản nháp chưa đủ

### Khi nhóm muốn GO nhưng kịch bản tệ nhất < 1,5

```text
Nhóm tôi muốn GO vì ROI cơ bản = 3,5:1.

NHƯNG kịch bản tệ nhất = 1,2:1 < 1,5:1.

Theo khung tiêu chí, đây là vùng CONDITIONAL:
- Cơ bản GO ngụ ý "vững qua mọi cú sốc".
- Tệ nhất < 1,5 ngụ ý "thử nghiệm có biên mỏng khi 2 cú sốc cùng xảy ra".

Verdict thành thật: CONDITIONAL, KHÔNG GO.

Lập luận với người mua:
- "ROI cơ bản 3,5:1 hấp dẫn."
- "Nhưng nếu tỷ lệ sử dụng < 40% VÀ chất lượng < 60% cùng lúc → ROI
  1,2:1 → mất 30% biên an toàn."
- "Đề xuất CONDITIONAL với điều kiện: theo dõi tỷ lệ sử dụng + chất
  lượng hàng tuần. Nếu cả 2 cùng giảm 2 tuần liên tiếp → kích hoạt xem
  lại."

CONDITIONAL với điều kiện cứng bảo vệ được hơn là GO không nén thử.

Đề xuất sửa verdict: CONDITIONAL.
```

### Khi nhóm muốn NO-GO sớm

```text
Nhóm tôi muốn NO-GO vì ROI cơ bản = 1,4:1 (cận biên).

Trước khi NO-GO, thử 3 hướng tăng:
- Giảm chi phí: đổi mô hình cao cấp → trung; bỏ công cụ không bắt buộc;
  đàm phán lại ràng buộc kiểm tra.
- Tăng giá trị: mở rộng thử nghiệm để rải triển khai tốt hơn; đào tạo
  để tăng tỷ lệ sử dụng; tinh chỉnh câu lệnh để tăng chất lượng.
- Kéo dài thời gian: thử nghiệm 90 → 180 ngày để rải triển khai gấp đôi.

Tính lại ROI với tổ hợp các hướng. Nếu sau điều chỉnh ROI > 2:1 →
CONDITIONAL. Nếu vẫn < 1,5:1 → NO-GO kèm 2–3 thay đổi đề xuất cụ thể.

Đừng NO-GO trước khi thử các hướng.
```

### Khi điều kiện đặt ra không khả thi

```text
Điều kiện CONDITIONAL nhóm tôi:
- Tỷ lệ sử dụng ≥ 80% trong tháng 1.
- Chất lượng ≥ 90% trong tháng 1.

Kiểm tra thực tế:
- Tỷ lệ sử dụng 80% trong tháng 1 ở thử nghiệm tự nguyện → KHÓ. Thực tế
  50–70% tháng 1.
- Chất lượng 90% cho việc viết nháp → KHÓ. Thực tế 75–85% khi ổn định,
  65–75% tháng 1.

Điều kiện này không khả thi → CONDITIONAL biến tướng thành NO-GO trá hình.

Sửa lại điều kiện:
- Tỷ lệ sử dụng ≥ 50% trong tháng 1, ≥ 65% trong tháng 3.
- Chất lượng ≥ 70% trong tháng 1, ≥ 80% trong tháng 3.

Điều kiện phải đạt được thực tế — không phải ước mơ.
```

---

## Trước khi dán kết quả vào worksheet — nhóm tự rà soát

- Verdict có rõ (GO / CONDITIONAL / NO-GO), không "có thể"?
- Tuyên bố có bảo vệ được trước câu hỏi từ người mua trong 3–4 câu?
- Mỗi điều kiện có chỉ số + thời gian + hành động khi không đạt?
- Điều kiện dừng có ngưỡng + thời gian + hành động cụ thể?
- Verdict có phản ánh dữ liệu, hay phản ánh "muốn pilot thành công"?

---

## Câu hỏi mở rộng (chỉ làm khi còn thời gian)

```text
Sau khi viết verdict, suy nghĩ 3 câu để chuẩn bị bảo vệ:

1. Câu hỏi khó từ người mua:
   - Giám đốc kỹ thuật: "Tại sao CONDITIONAL chứ không phải GO?"
   - Giám đốc tài chính: "Kịch bản tệ nhất 0,6:1 — thử nghiệm có thật sự
     an toàn không?"
   - Phó tổng vận hành: "Tỷ lệ sử dụng 60% trong tháng 1 — dựa trên gì?"
   - Chuẩn bị 1–2 câu trả lời cho mỗi câu.

2. Câu hỏi từ hội đồng D28:
   - "Nếu chi phí API tăng 5×, thử nghiệm có sống không?"
   - "Tỷ lệ sử dụng ở sản xuất chính thức khác thử nghiệm thế nào?"
   - "1 năm sau ROI có đổi không?"

3. Phản biện ngược:
   - "ROI 2:1 vẫn nhỏ — có nên không làm, dồn nguồn lực vào dự án khác?"
   - Đáp: "ROI 2:1 + giá trị tuỳ chọn. Đối thủ làm trước → chi phí của
     việc không thử."
   - "Tỷ lệ sử dụng 30% là chế độ thất bại — kế hoạch chuyển đổi?"

3 câu này chuẩn bị phòng thủ rõ cho D28 — không chỉ đọc verdict mà phản
ứng thông minh.
```
