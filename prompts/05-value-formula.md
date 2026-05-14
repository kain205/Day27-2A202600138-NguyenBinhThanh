# Câu lệnh AI 5 — Tính giá trị mỗi tháng AI mang lại

**Dùng khi**: Bước 2 Lab, sau khi đã có mô hình định giá và chi phí — nhóm cần tính giá trị thực tế AI mang lại mỗi tháng để làm đầu vào cho ROI.

**Công cụ gợi ý**: Claude, ChatGPT.

**Lưu kết quả vào**: phần C.1–C.5 trong `worksheet/02-pricing-value/3-FINAL-pricing-value-roi.md`.

**Thời gian**: 15 phút.

---

## Trước khi vào câu lệnh — 5 câu nhóm tự trả lời

Đây là phần dễ bị đẹp giả nhất trong cả Lab. 90% nhóm phóng đại giá trị vì dùng "thời gian tiết kiệm thô" (Gross) thay vì "thời gian tiết kiệm thực" (NET sau khi trừ chờ AI, người kiểm tra, đổi tab, làm lại). Hoặc giả định tỷ lệ sử dụng 100%, chất lượng AI 95%. Đây là sai lầm khiến ROI quá đẹp ở kịch bản cơ bản — nhưng sụp khi nén thử.

1. Thời gian xử lý một việc khi chưa có AI (lấy từ trường 2 đề bài): ___ phút.
2. Đã ước lượng từng phần để trừ khỏi thời gian tiết kiệm thô chưa — chờ AI / người kiểm tra / đổi tab / làm lại?
3. Tiền công mỗi giờ đã cộng phụ phí: $___/giờ (= cơ bản × 1,3–1,5).
4. Tỷ lệ sử dụng thực tế có thực tế không (60–85% bắt buộc, 30–60% tuỳ chọn, 20–50% thói quen mới, 50–80% có thưởng thử nghiệm)?
5. Hệ số chất lượng có thực tế không (80–95% phân loại, 60–80% viết nháp, 70–85% tóm tắt, 50–70% sáng tạo, 40–65% phức tạp)?

---

## Câu lệnh chính (dán sau kết quả mô hình định giá)

```text
Bạn là Product Manager AI có kinh nghiệm tính ROI cho sản phẩm AI.
Dựa trên bối cảnh ở trên (đề bài + Cost Model + mô hình định giá),
giúp nhóm tôi tính GIÁ TRỊ THỰC mỗi tháng — bảo thủ, không phóng đại.

Phần 1 — Bóc tách thời gian tiết kiệm:
Tính thời gian tiết kiệm THỰC mỗi việc (không phải thô):

| Phần | Phút | Lý do |
|---|---|---|
| Thời gian xử lý gốc (chưa có AI) | ___ | Từ trường 2 đề bài |
| − Chờ AI phản hồi | ___ | Độ trễ Claude/GPT ~5–30 giây = 0,1–0,5 phút |
| − Người kiểm tra | ___ | Nếu có ràng buộc duyệt (~1–5 phút/việc) |
| − Đổi tab / dán dữ liệu | ___ | Mở AI ngoài, dán vào, dán lại (~0,5–1 phút) |
| − Làm lại khi chất lượng kém | ___ | Thời gian sửa × tỷ lệ chất lượng kém |
| = Thời gian tiết kiệm THỰC | ___ | tổng |

Quy tắc cứng:
- Thời gian tiết kiệm thực thường = 40–60% thời gian thô. Nếu nhóm tôi
  tính ra > 80% → đã quên một phần phụ phí.
- Đừng bỏ qua phần đổi tab — đây là chi phí ẩn quan trọng.

Phần 2 — Tiền công mỗi giờ (đã cộng phụ phí):
- Lương cơ bản: $___/giờ (từ đề bài hoặc mức tham khảo ngành).
- Hệ số phụ phí: × 1,3–1,5 (bảo hiểm, thuế, quản lý, văn phòng).
- = Tiền công đầy đủ: $___/giờ.

Nếu đề bài không cho lương, dùng:
- Mỹ: nhân viên hỗ trợ $20–30/h, luật sư $80–150/h, y tá $40–60/h.
- Việt Nam: nhân viên hỗ trợ $5–10/h, luật sư $30–50/h, y tá $15–25/h.

Phần 3 — Tỷ lệ sử dụng thực tế:
- Khoảng tham khảo cho đề bài tôi: ___%.
- Đề bài có bắt buộc dùng không? Có ưu đãi không?
- Tháng 1 (đầu): ___%.
- Tháng 3 (ổn định): ___%.
- Trung bình cho cả thời gian thử nghiệm: ___%.

Nêu lý do trong 1–2 câu — không chỉ một con số.

Phần 4 — Hệ số chất lượng:
- Loại việc: phân loại / viết nháp / tóm tắt / sáng tạo / phức tạp (chọn 1).
- Khoảng tham khảo: ___%.
- Bối cảnh đề bài: dữ liệu sẵn có thế nào (vd: 50K lịch sử ticket — tốt
  cho viết nháp), tài liệu nội bộ có cũ không, ngành có hẹp không.
- Hệ số chất lượng thực tế cho đề bài: ___%.

Phần 5 — Công thức giá trị mỗi tháng:
Tính từng bước:

Bước 1: Giá trị thô mỗi tháng
= Khối lượng/tháng × Thời gian tiết kiệm thực × (Tiền công/giờ ÷ 60)
= ___ × ___ × ($___/60) = $___

Bước 2: Điều chỉnh theo tỷ lệ sử dụng và chất lượng
= Bước 1 × Tỷ lệ sử dụng × Chất lượng
= $___ × ___% × ___% = $___

Bước 3: Trừ chi phí làm lại (nếu chưa trừ trong thời gian tiết kiệm thực)
− $___

= Giá trị THỰC mỗi tháng: $___

Phần 6 — Phân tích nhạy cảm:
- Nếu tỷ lệ sử dụng đổi ±20%, giá trị thực đổi bao nhiêu?
- Nếu chất lượng đổi ±20%, giá trị thực đổi bao nhiêu?
- Biến nào nhạy nhất → đó là chỉ số phải theo dõi chặt nhất trong pilot.

Yêu cầu trình bày:
- Mỗi số có công thức rõ.
- Mỗi % có lý do 1–2 câu.
- Viết tiếng Việt thoát nghĩa.

Yêu cầu phản biện:
- Thời gian tiết kiệm thực có > 80% thô không? (Nếu có → kiểm tra lại
  phụ phí đã trừ chưa.)
- Tỷ lệ sử dụng > 80% có dữ liệu cứng nào không?
- Chất lượng > 85% có dữ liệu thử thực tế nào không?
- Có tính làm lại 2 lần không (1 lần trong thời gian thực + 1 lần ở
  bước 3)?
```

---

## Iterate — đẩy AI sâu hơn khi bản nháp chưa đủ

### Khi nhóm muốn chất vấn tỷ lệ sử dụng

```text
Nhóm tôi đặt tỷ lệ sử dụng = 70% cho pilot. Lý do là:

Trả lời 5 câu:
1. Thử nghiệm có bắt buộc dùng AI không, hay tuỳ chọn?
2. Người dùng đã có kinh nghiệm dùng công cụ AI trước đó chưa?
3. Giao diện AI có tích hợp sẵn vào quy trình (vd: trong Zendesk), hay
   phải mở tab riêng?
4. Có thưởng / ưu đãi cho người dùng chịu thử không?
5. Có buổi đào tạo không? Mấy buổi?

Dựa trên trả lời, tỷ lệ thực tế là:
- Tuỳ chọn + không tích hợp + không thưởng → 20–40%.
- Tuỳ chọn + có tích hợp + thưởng nhẹ → 40–60%.
- Bắt buộc + tích hợp + có đào tạo → 60–85%.

70% rơi vào tầng 3 — cần lý do bắt buộc + tích hợp + đào tạo cụ thể
trong đề bài để biện minh.
```

### Khi nhóm muốn đối chiếu chất lượng với mức tham khảo

```text
Chất lượng nhóm tôi đặt = 80%. Đối chiếu:

Loại việc: viết nháp trả lời ticket support.

Mức tham khảo:
- Claude 3.5 trên ngành chung: 75–85% (theo công bố đánh giá).
- Claude 3.5 đã tinh chỉnh trên ngành support: 85–92%.
- Đề bài của tôi: dùng Claude 3.5 cơ bản + tìm tài liệu nội bộ → kỳ vọng
  70–82% (vì tài liệu nội bộ cũ 30%).

Chất lượng cho đề bài:
- Tháng 1 (đầu): 70% (ngữ cảnh tìm tài liệu chưa tối ưu).
- Tháng 3 (ổn định): 80% (sau khi tinh chỉnh câu lệnh).
- Trung bình thử nghiệm: 75%.

Nhóm nên dùng 75% thay vì 80% — bảo thủ hơn, sát thực tế hơn.
```

### Khi thời gian tiết kiệm thực > 80% thô (đáng nghi)

```text
Nhóm tôi tính ra: thực = 10 phút, thô = 12 phút → 83% — đáng nghi.

Bình thường tỷ lệ thực/thô = 40–60%. Kiểm tra lại:

1. Đã trừ thời gian người kiểm tra chưa?
   - Nếu đề bài có "người duyệt trước khi gửi" → thường 2–4 phút.
2. Đã trừ thời gian đổi tab chưa?
   - Phải mở Zendesk → mở AI → dán lại? Hay AI tích hợp inline?
3. Đã trừ thời gian làm lại chưa?
   - Chất lượng 80% → 20% nháp không dùng được, phải viết tay → thời
     gian sửa.

Tính lại với 3 phụ phí:
- Thô: 12 phút (tìm tài liệu 5 + viết nháp 4 + gửi 3).
- AI tiết kiệm: 5 + 4 = 9 phút tiềm năng.
- Chờ AI: 0,3 phút.
- Kiểm tra: 2 phút.
- Đổi tab: 0,3 phút (tích hợp inline → nhẹ).
- Làm lại trung bình: 0,5 phút (= 2 phút sửa × 20% / 80% giữ).

Thực = 9 − 0,3 − 2 − 0,3 − 0,5 = 5,9 phút.
Thực/thô = 5,9/12 = 49%. Khớp tham khảo 40–60%. ✓
```

---

## Trước khi dán kết quả vào worksheet — nhóm tự rà soát

- Thời gian tiết kiệm thực rơi vào 40–60% thô không?
- Tỷ lệ sử dụng < 80% (nếu cao hơn có dữ liệu cứng không)?
- Chất lượng < 85% (nếu cao hơn có dữ liệu thử thực tế không)?
- Mỗi % có 1–2 câu lý do?
- Có tính làm lại 2 lần (1 trong thời gian thực + 1 ở bước 3) không?

---

## Câu hỏi mở rộng (chỉ làm khi còn thời gian)

```text
Sau khi tính giá trị, suy nghĩ 3 góc:

1. Giá trị ẩn (không phải thời gian tiết kiệm):
   - Chất lượng đều hơn (giảm độ chênh) → biện minh được trong rubric mới.
   - Đào tạo nhân viên mới nhanh hơn (3 tuần → 1 tuần) → tiết kiệm chi
     phí đào tạo.
   - 24/7 (AI không nghỉ) → phục vụ ngoài giờ.
   - Tăng được khối lượng (10× không cần tuyển thêm) → hoãn tuyển dụng.

2. Thời gian tiết kiệm vs Giá trị tạo ra — 2 thứ khác nhau:
   - Tiết kiệm: nhân viên dùng AI → tiết kiệm 7 phút/ticket → giá trị =
     7 phút × tiền công.
   - Tạo ra: nhân viên dùng thời gian tiết kiệm làm gì? Nhận thêm ticket?
     Việc khác có giá trị hơn? Hay là đi cà phê?
   - Nếu chỉ "đi cà phê" → giá trị không thật sự hiện hữu.

3. Giá trị gián tiếp:
   - AI giảm tỷ lệ khách rời (vì điểm hài lòng tăng), tăng tỷ lệ chốt deal
     (vì phản hồi nhanh).
   - Nếu đề bài có "khách rời 18% do hỗ trợ kém" → AI giảm 2 điểm % →
     tiết kiệm bao nhiêu giá trị vòng đời khách hàng?
   - Giá trị gián tiếp có thể lớn hơn giá trị thời gian tiết kiệm trực tiếp.

3 câu này giúp hiểu giá trị đầy đủ — không chỉ "thời gian × tiền công".
```
