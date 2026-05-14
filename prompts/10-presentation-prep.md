# Câu lệnh AI 10 — Chuẩn bị bài trình bày 3 phút

**Dùng khi**: nhóm đã có Economics Sheet đầy đủ, cần chuẩn bị bài trình bày 6 phút (~3 phút trình bày + ~3 phút hỏi đáp) cho phần present cuối Lab.

**Công cụ gợi ý**: Claude, ChatGPT.

**Lưu kết quả vào**: ghi chú riêng / file slide riêng — không trong worksheet.

**Thời gian**: 10–15 phút.

---

## Trước khi vào câu lệnh — 5 câu nhóm tự trả lời

Bài 3 phút phải CHẶT. Mỗi giây đều có giá. Không lan man, không "uhm uhm". Trả lời 5 câu này trước để biết phần nào nhóm đã thuộc, phần nào còn phải tập.

1. Có thể bị giảng viên gọi bất chợt không? Theo dàn bài, giảng viên chọn 4 cặp trình bày.
2. Số đề bài + Usage Unit + ROI cơ bản + verdict — đã thuộc lòng chưa?
3. Kịch bản tệ nhất + ROI mới — đã thuộc lòng chưa?
4. 3 điều kiện cứng nhất (nếu CONDITIONAL) — đã thuộc lòng chưa?
5. Người mua trong đề bài là ai, họ sẽ hỏi gì — đã dự đoán chưa?

---

## Câu lệnh chính (dán sau Economics Sheet cuối cùng)

```text
Bạn là huấn luyện viên thuyết trình cho PM AI.
Dựa trên Economics Sheet đã hoàn thành, giúp nhóm tôi chuẩn bị bài
trình bày 3 phút + 3 phút hỏi đáp.

Phần 1 — Dàn bài 3 phút (timing cứng):

0:00 — 0:30  Đề bài + Usage Unit
              "Đề bài #___ [tên]. Tình huống: [1 câu]. Usage Unit: [1 câu]."

0:30 — 1:00  Cost Model
              "Chi phí/tháng $___. Trong đó: API $___ (___%), công cụ
              $___, người kiểm tra $___ (___%), triển khai $___."
              [Bài học: chi phí chủ yếu là ___]

1:00 — 1:30  Giá trị / ROI
              "Giá trị/tháng $___ với tỷ lệ sử dụng ___%, chất lượng
              ___%. ROI cơ bản ___:1."
              [Bài học: ROI nhạy nhất với ___]

1:30 — 2:00  Kịch bản tệ nhất
              "Kết hợp tệ nhất [tên 2 kịch bản] → ROI ___:1."
              [Bài học: kịch bản đau nhất là ___]

2:00 — 3:00  Verdict + Điều kiện
              "Verdict: [GO / CONDITIONAL / NO-GO]."
              "Lý do: [ROI cơ bản + ROI tệ nhất]."
              "Điều kiện: 1) ___ 2) ___ 3) ___."
              "Cắt nếu: ___."

3:00          DỪNG. Im lặng. Đợi hỏi đáp.

Yêu cầu: viết kịch bản đầy đủ 3 phút, dùng số liệu thật của đề bài nhóm
tôi.

Phần 2 — Slide (6 trang đơn giản):

Trang 1: Tiêu đề + Đề bài #
Trang 2: Phân bổ chi phí (biểu đồ thanh hoặc danh sách)
Trang 3: Công thức giá trị + ROI
Trang 4: Bảng 5 kịch bản, làm nổi bật kịch bản tệ nhất
Trang 5: Tuyên bố verdict + 3 điều kiện
Trang 6: Mời hỏi đáp

Viết nội dung từng trang (tối đa 5–7 dòng/trang).

Phần 3 — Dự đoán 5 câu hỏi từ giảng viên:

Giảng viên thường hỏi 4 nhóm câu:
1. Chất vấn giả định (tỷ lệ sử dụng, chất lượng, chi phí mỗi lần chạy).
2. Chất vấn nén thử (kịch bản tệ nhất, cách giảm thiểu, điểm hoà vốn).
3. Chất vấn chiến lược (rủi ro nhà cung cấp, mở rộng quy mô, CONDITIONAL).
4. Chất vấn so sánh (so với cặp khác đề bài).

Chuẩn bị 5 câu hỏi-đáp:

Hỏi 1: "Tỷ lệ sử dụng ___% — dựa trên gì? Có dữ liệu không?"
Đáp 1: [1–2 câu, có dữ liệu hoặc lý do]

Hỏi 2: "Kịch bản nào đau nhất? Vì sao?"
Đáp 2: [kịch bản + lý do + bài học]

Hỏi 3: "Kết hợp tệ nhất ___:1 — thử nghiệm có an toàn không?"
Đáp 3: [bảo vệ bằng điều kiện + điểm cắt]

Hỏi 4: "Chi phí nhà cung cấp × 2 — bài học Replit biên âm — tránh thế nào?"
Đáp 4: [giảm thiểu: ký hợp đồng / mô hình dự phòng / theo dõi cổng chi phí]

Hỏi 5: "Verdict CONDITIONAL — khi nào xem lại? Chỉ số cắt là gì?"
Đáp 5: [mốc thời gian + điểm cắt cụ thể]

Phần 4 — Phản hồi kiểu huấn luyện viên:

Sau khi viết kịch bản + slide, xác định 3 điểm yếu:
- "Đoạn nào dài quá / nói nhanh quá?"
- "Số nào người nghe khó nắm bắt? Cần biểu đồ hỗ trợ?"
- "Giọng có quá lạc quan / bi quan không?"

Đề xuất chỉnh sửa.

Yêu cầu trình bày:
- Kịch bản bằng tiếng Việt thoát nghĩa (giả định trình bày bằng tiếng
  Việt cho lớp).
- Nội dung slide ngắn gọn 5–7 dòng.
- Hỏi đáp phòng thủ có dữ liệu rõ ràng.

Yêu cầu phản biện:
- Trong 3 phút, có thông tin nào nên cắt (biết-thêm-cũng-được, không
  phải cần-biết)?
- Verdict có rõ ở đầu và cuối không?
- Điều kiện có cụ thể để người nghe nhớ được không?
```

---

## Iterate — đẩy AI sâu hơn khi bản nháp chưa đủ

### Khi kịch bản dài hơn 3 phút

```text
Kịch bản bạn viết dài ___ từ → ___ phút (trung bình 150 từ/phút tiếng Việt).

Vượt 3 phút. Cắt:

Phải giữ (cốt lõi):
- Đề bài # + Usage Unit (30 giây).
- Số chi phí + phần chiếm phần lớn (30 giây).
- ROI cơ bản + giả định tỷ lệ sử dụng / chất lượng (30 giây).
- Kịch bản tệ nhất + ROI (30 giây).
- Verdict + 3 điều kiện + điểm cắt (60 giây).

Có thể cắt nếu thiếu thời gian:
- Phân tích chi tiết 4 phần chi phí.
- Cả 5 kịch bản nén thử (chỉ kể kịch bản tệ nhất).
- Chi tiết sản phẩm đối chiếu thực.
- Bảng nhạy cảm chi tiết.

Viết lại kịch bản chặt trong 3 phút, dùng nội dung cốt lõi.
```

### Khi muốn phòng thủ hỏi đáp mạnh hơn

```text
Hỏi đáp giảng viên thường có 4 nhóm câu. Cho mỗi nhóm, viết 2 cặp hỏi-đáp
ngắn (mỗi đáp 1–2 câu, có dữ liệu cụ thể):

1. Chất vấn giả định: tỷ lệ sử dụng / chất lượng dựa trên gì?
   → Đáp: tham khảo + bối cảnh đề bài + ngưỡng bảo thủ.

2. Chất vấn nén thử: kịch bản nào đau nhất, giảm thiểu thế nào?
   → Đáp: tên kịch bản + lý do + 3 hành động giảm thiểu cụ thể.

3. Chất vấn chiến lược: mở rộng quy mô / đổi nhà cung cấp ảnh hưởng gì?
   → Đáp: phần chi phí nào nhạy với điều đó + con số tác động.

4. So sánh chéo: đề bài khác có quy luật tương tự không?
   → Đáp: 1 quy luật chung từ 3 đề bài.

Viết 8 câu phòng thủ ngắn — chuẩn bị cho mọi nhóm chất vấn.
```

---

## Trước khi tập trình bày — nhóm tự rà soát

- Kịch bản trong 3 phút chặt (150 từ/phút × 3 = ~450 từ)?
- Verdict có ở đầu và cuối, lặp lại 2 lần?
- 3–5 con số chính (chi phí, giá trị, ROI cơ bản, ROI tệ nhất, ngưỡng tỷ lệ sử dụng) — đã thuộc lòng chưa?
- 5 câu hỏi đáp cover 4 nhóm chất vấn?
- Nhóm có thể bảo vệ nếu giảng viên hỏi sâu hơn không?

Tự kiểm tra:
- Đọc kịch bản với đồng hồ → có đúng 3 phút không?
- Cặp tự hỏi đáp nhau 5 câu → có phòng thủ rõ không?

---

## Câu hỏi mở rộng (chỉ làm khi còn thời gian)

```text
Sau khi chuẩn bị, tập thêm 3 góc cho bài "ấn tượng" thay vì chỉ "ổn":

1. Câu mở (5 giây đầu):
   - Cách 1: "Đề bài 1 là ___" — mở chán.
   - Cách 2: "ROI cơ bản 2,07:1 — nhưng kịch bản tệ nhất 0,6. Đó là lý
     do CONDITIONAL." — mở có sức căng.
   - Đề xuất câu mở cho đề bài nhóm tôi.

2. Câu chốt (5 giây cuối):
   - Cách 1: "Verdict CONDITIONAL." — đóng nhạt.
   - Cách 2: "Thử nghiệm sống nếu tỷ lệ sử dụng ≥ 60%. Đó là lý do
     CONDITIONAL — không phải GO. Tỷ lệ sử dụng là biến cứu nguy." —
     đáng nhớ.
   - Đề xuất câu chốt cho đề bài nhóm tôi.

3. Dự phòng tinh thần:
   - Nếu giảng viên hỏi câu nhóm chưa chuẩn bị: chiến thuật là gì?
   - "Câu hỏi hay. Tôi chưa mô hình hoá câu đó cụ thể, nhưng dựa trên
     khung: ___."
   - "Tôi sẽ thử kịch bản này sau buổi và cập nhật vào Economics Sheet."

3 góc này = đánh bóng bài trình bày từ "ổn" thành "ấn tượng".
```
