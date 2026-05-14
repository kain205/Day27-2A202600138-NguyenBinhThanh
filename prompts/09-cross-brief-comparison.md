# Câu lệnh AI 9 — So sánh với cặp khác đề bài

**Dùng khi**: nhóm đã hoàn thành Economics Sheet và muốn đối chiếu kết quả với 1–2 cặp ở đề bài khác — để rút ra quy luật chung về kinh tế AI.

**Công cụ gợi ý**: Claude, ChatGPT.

**Lưu kết quả vào**: phần "So sánh với cặp khác đề bài" trong `04-FINAL-economics-sheet.md`.

**Thời gian**: 10 phút (sau giờ Lab chính, có thể làm trong giờ trình bày).

---

## Trước khi vào câu lệnh — 5 câu nhóm tự trả lời

So sánh không phải để "thắng / thua" giữa nhóm. Để rút ra quy luật chung **vượt qua một đề bài cụ thể** — đây là loại bài học quan trọng nhất cho người làm sản phẩm AI sau này.

1. Đề bài nhóm tôi là gì (số + tên ngắn)?
2. 2 cặp khác đã chia sẻ kết quả với nhóm là đề bài gì?
3. 3 chỉ số chính so sánh: Chi phí/tháng, Giá trị/tháng, ROI.
4. Quy luật cần tìm: cấu trúc chi phí khác nhau ở điểm nào? Verdict khác nhau vì lý do gì?
5. Mục tiêu cuối: tổng quát hoá quy luật từ 3 đề bài.

---

## Câu lệnh chính (dán sau khi đã có Economics Sheet của cả 3 đề bài)

```text
Bạn là Senior Product Manager AI có kinh nghiệm nhìn nhiều dự án.
Dựa trên Economics Sheet của 3 đề bài (đề bài nhóm tôi + 2 đề bài cặp
khác), giúp tôi rút quy luật và bài học.

Dữ liệu đầu vào:

Đề bài A (nhóm tôi): #___ "[tên]"
- Usage Unit: ___
- Chi phí/tháng: $___ (API ___%, công cụ ___%, người kiểm tra ___%, triển khai ___%)
- Giá trị/tháng: $___
- ROI cơ bản: ___:1
- Verdict: ___
- Mô hình định giá: ___

Đề bài B (cặp khác): #___ "[tên]"
- (như trên)

Đề bài C (cặp khác): #___ "[tên]"
- (như trên)

Yêu cầu phân tích:

Phần 1 — Bảng so sánh:

| Mặt | Đề A | Đề B | Đề C |
|---|---|---|---|
| Ngành | | | |
| Usage Unit | | | |
| Khối lượng/tháng | | | |
| Chi phí/lần chạy | $___ | $___ | $___ |
| Phần chi phí chiếm phần lớn | (vd: API / Người kiểm tra / Công cụ) | | |
| Chi phí/tháng | $___ | $___ | $___ |
| Giá trị/tháng | $___ | $___ | $___ |
| ROI cơ bản | ___:1 | ___:1 | ___:1 |
| ROI kịch bản tệ nhất | ___:1 | ___:1 | ___:1 |
| Mô hình định giá | | | |
| Verdict | | | |

Phần 2 — Tìm 3–4 quy luật:

Quy luật 1 — Cấu trúc chi phí:
- Đề bài nào chi phí chủ yếu là API? Lý do? (vd: khối lượng cao + ít
  kiểm tra → API chiếm phần lớn).
- Đề bài nào chi phí chủ yếu là Người kiểm tra? Lý do? (vd: ràng buộc
  100% người duyệt).
- Đề bài nào chi phí chủ yếu là Công cụ? Lý do?

Quy luật 2 — Khối lượng vs Chi phí/lần chạy:
- Đề bài khối lượng cao + chi phí/lần thấp (support, kiểm duyệt nội dung)
  vs đề bài khối lượng thấp + chi phí/lần cao (luật, y tế)?
- Hai mô hình kinh tế khác nhau — đánh đổi gì cho mỗi mô hình?

Quy luật 3 — Verdict:
- Đa số verdict là gì (GO / CONDITIONAL / NO-GO)?
- Quy luật nào dẫn đến CONDITIONAL (vd: 3 trong 4 = CONDITIONAL nếu có
  ràng buộc kiểm tra)?

Quy luật 4 — Mô hình định giá:
- Đề bài có gắn-rõ-với-AI cao (luật, bồi thường) → tính theo kết quả dễ
  hơn?
- Đề bài có gắn-rõ thấp (support, nội dung) → tính theo người dùng dễ
  hơn?
- Có ngoại lệ nào không?

Phần 3 — 3 bài học có thể chuyển sang đề khác:

1. (vd: "Kinh tế AI bị chi phối bởi người kiểm tra khi đề bài có ràng
   buộc 100% duyệt. Chi phí API thường không đáng kể.")

2. (vd: "ROI nhạy nhất với tỷ lệ sử dụng — không phải chi phí. Tỷ lệ
   sử dụng tăng 20% → ROI tăng 30%, nhưng chi phí giảm 20% chỉ làm ROI
   tăng 20%.")

3. (vd: "CONDITIONAL chiếm 70% verdict — đó là thực tế, không phải bi
   quan. Pilot AI đa số là CONDITIONAL.")

Phần 4 — Bài học cho người mua:

Nếu giám đốc kỹ thuật / phó tổng hỏi "Quy luật giữa các thử nghiệm AI
của chúng ta là gì?", trả lời:
- (vd: "Chi phí người kiểm tra chiếm phần lớn. Tối ưu ROI = tối ưu quy
  trình kiểm tra, không phải chọn mô hình rẻ nhất.")
- (vd: "Tỷ lệ sử dụng là biến quan trọng nhất. Đầu tư đào tạo > đầu tư
  chất lượng AI.")

Phần 5 — Có gì áp dụng được cho nhóm tôi:

So với đề B + C, đề A:
- Mạnh hơn ở: ___
- Yếu hơn ở: ___
- Có thể vay mượn từ B/C: ___ (vd: mô hình định giá, điều kiện giảm
  thiểu).

Yêu cầu trình bày:
- Bảng + gạch đầu dòng rõ ràng.
- Viết tiếng Việt thoát nghĩa.

Yêu cầu phản biện:
- Có quy luật nào chỉ là trùng hợp ngẫu nhiên không (mẫu chỉ 3 đề bài)?
- Có quy luật nào bất ngờ không?
- Quy luật nào ngược lại với "trí khôn thông thường"?
```

---

## Iterate — đẩy AI sâu hơn khi bản nháp chưa đủ

### Khi muốn rút kết luận vĩ mô từ 3 đề bài

```text
Sau khi phân tích, rút 3 kết luận có bằng chứng từ 3 đề bài:

1. "Chi phí AI bị chi phối bởi cấu trúc ràng buộc — không phải API."
   - Bằng chứng: bao nhiêu trong 3 đề bài có người kiểm tra chiếm phần lớn?
   - Hệ quả cho PM: tối ưu quy trình kiểm tra trước, chọn mô hình rẻ sau.

2. "Điểm hoà vốn thường ở tỷ lệ sử dụng khoảng ___%."
   - Bằng chứng: cả 3 đề bài hoà vốn ở mức tương tự?
   - Hệ quả: chỉ số quan trọng nhất = theo dõi tỷ lệ sử dụng.

3. "Mô hình định giá phụ thuộc trục Attribution nhiều hơn Autonomy."
   - Bằng chứng: gắn-rõ cao → tính theo kết quả; gắn-rõ thấp → tính theo
     người.

3 kết luận này có bảo vệ được với dữ liệu 3 đề bài không?
```

### Khi muốn đối chiếu với sản phẩm thật ngoài lớp

```text
Cho mỗi đề bài, tìm 1 sản phẩm AI thật cùng ngành (Intercom Fin / Hive
AI / Harvey AI / Buoy Health / …).

So sánh: quy luật của lớp giống / khác ngành ở điểm nào? Lý do (thường
là thử nghiệm nhỏ vs sản xuất quy mô lớn)? Bài học cho nhóm tôi.
```

---

## Trước khi dán kết quả vào worksheet — nhóm tự rà soát

- Quy luật rút ra có phải thực sự là quy luật, hay chỉ là trùng hợp?
- Bài học có hành động được cho PM tương lai không?
- Có quy luật nào bất ngờ, ngược trí khôn thông thường không?
- Bài học cho nhóm có cụ thể không, hay chỉ là chung chung?

---

## Câu hỏi mở rộng (chỉ làm khi còn thời gian)

```text
So sánh giữa các đề bài là cách để trả lời 1 câu hỏi lớn hơn:

"Có quy luật chung 'AI đắt / rẻ' không, hay luôn phụ thuộc bối cảnh?"

Sau khi xem 3 đề bài, trả lời:

1. Phép thử quy luật chung:
   - Nếu nói "Chi phí AI luôn bị chi phối bởi API" — có đúng không?
   - Bằng chứng: 3/3 đề bài lớp tôi chi phí chủ yếu là người kiểm tra,
     không phải API.
   - Kết luận: câu này SAI. Chi phí AI bị chi phối bởi CẤU TRÚC RÀNG BUỘC
     (có người kiểm tra hay tự chủ).

2. Riêng từng loại đề bài:
   - Đề có 100% người kiểm tra → người kiểm tra chiếm phần lớn.
   - Đề tự chủ cao → API chiếm phần lớn.
   - Đề ngành hẹp → triển khai chiếm phần lớn (chi phí tinh chỉnh).

3. Tư duy của PM AI:
   - Trước nén thử: cứ tưởng "Chi phí AI = chi phí API".
   - Sau nén thử: "Chi phí AI = chi phí ràng buộc + chi phí cơ hội".
   - Đây là bước chuyển tư duy quan trọng cho PM AI mới.
```
