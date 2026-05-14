# Câu lệnh AI 6 — Tính tỷ lệ ROI và điểm hoà vốn

**Dùng khi**: Bước 2 Lab, sau khi đã có chi phí mỗi tháng và giá trị mỗi tháng — nhóm cần tính ROI, đánh giá tầng kết quả và tìm điểm hoà vốn.

**Công cụ gợi ý**: Claude, ChatGPT.

**Lưu kết quả vào**: phần C.6 và C.7 trong `worksheet/02-pricing-value/3-FINAL-pricing-value-roi.md`.

**Thời gian**: 10 phút.

---

## Trước khi vào câu lệnh — 5 câu nhóm tự trả lời

ROI quá đẹp hay quá tệ đều là cảnh báo. ROI > 20:1 thường có nghĩa là nhóm đã phóng đại giá trị; ROI < 1:1 nghĩa là cần xoay (pivot) hoặc tìm cách giảm chi phí. Trả lời 5 câu này trước khi để AI giúp.

1. Chi phí mỗi tháng đã tính: $___.
2. Giá trị mỗi tháng đã tính: $___.
3. Tỷ lệ ROI = giá trị / chi phí = ___:1. (Tự tính trước bằng tay.)
4. Tỷ lệ này rơi vào tầng nào (xem bảng tham chiếu trong `3-FINAL-pricing-value-roi.md`)?
5. So với ngành / quy mô đề bài, tỷ lệ này có hợp lý không?

---

## Câu lệnh chính (dán sau kết quả Cost và Value)

```text
Bạn là cố vấn tài chính cho sản phẩm AI.
Dựa trên bối cảnh ở trên (đề bài + Cost Model + giá trị thực mỗi tháng),
giúp nhóm tôi tính ROI và đọc kết quả.

Phần 1 — Tỷ lệ ROI:
ROI = Giá trị/tháng ÷ Chi phí/tháng.

Nhóm tôi có:
- Chi phí/tháng: $___
- Giá trị/tháng: $___
- ROI = ___:1

Kiểm tra công thức: chỉ chia Giá trị/Chi phí — KHÔNG phải (Giá trị − Chi
phí)/Chi phí (đó là tỷ suất lợi nhuận, không phải ROI).

Phần 2 — Đọc tầng kết quả:

| Khoảng ROI | Diễn giải | Xu hướng verdict |
|---|---|---|
| > 5:1 | Mạnh | GO (nhưng kiểm tra có phóng đại không) |
| 3–5:1 | Vững | GO |
| 1,5–3:1 | Cận biên | CONDITIONAL |
| 1–1,5:1 | Yếu | CONDITIONAL chặt |
| < 1:1 | Âm | NO-GO |
| > 20:1 | Có thể phóng đại | Kiểm tra giả định |

ROI nhóm tôi rơi vào tầng nào? Xu hướng verdict là gì?

Phần 3 — Kiểm tra lại giả định:

Trả lời 5 câu:
1. Có phóng đại tỷ lệ sử dụng (> 80%) không?
2. Có phóng đại chất lượng (> 85%) không?
3. Có dùng thời gian tiết kiệm thô thay vì thực không?
4. Có quên phần nào trong chi phí (người kiểm tra, triển khai, giám sát)?
5. Có sai tiền công mỗi giờ (chỉ dùng lương cơ bản, quên hệ số phụ phí)?

Nếu CÓ bất kỳ câu nào → tính lại ROI với giả định bảo thủ hơn → ROI mới
bao nhiêu?

Phần 4 — Phân tích điểm hoà vốn:

Ở mức chất lượng cơ bản, tỷ lệ sử dụng phải đạt bao nhiêu để ROI = 1:1?

Công thức:
ROI = 1 = Giá trị / Chi phí
   = (Giá trị thô × Tỷ lệ sử dụng × Chất lượng) / Chi phí
=> Tỷ lệ sử dụng = Chi phí / (Giá trị thô × Chất lượng)

Tính cho nhóm: ___%

Diễn giải: "Nếu tỷ lệ sử dụng < ___% → thử nghiệm thất bại (giá trị <
chi phí)."

Ở mức tỷ lệ sử dụng cơ bản, chất lượng phải đạt bao nhiêu để ROI = 1:1?

Tính cho nhóm: ___%. Diễn giải tương tự.

Phần 5 — Bảng phân tích nhạy cảm:

| Tỷ lệ sử dụng | Chất lượng 60% | 70% | 80% | 90% |
|---|---|---|---|---|
| 30% | ___:1 | ___:1 | ___:1 | ___:1 |
| 50% | ___:1 | ___:1 | ___:1 | ___:1 |
| 70% | ___:1 | ___:1 | ___:1 | ___:1 |
| 90% | ___:1 | ___:1 | ___:1 | ___:1 |

Tìm "vùng đẹp" — tổ hợp tỷ lệ sử dụng + chất lượng nào cho ROI > 3:1.

Phần 6 — So với ngành:
- SaaS B2B trưởng thành: ROI ~3–5:1 (đã tính đủ chi phí).
- AI thử nghiệm nhỏ: thường 1–3:1 (chi phí rải đều cao).
- AI quy mô doanh nghiệp: thường 5–10:1.

Nếu ROI nhóm tôi quá cao hoặc quá thấp so với ngành → cảnh báo bất thường.

Yêu cầu trình bày:
- Mỗi phép tính có công thức.
- Mỗi nhận xét có 1–2 câu lý do.
- Viết tiếng Việt thoát nghĩa.

Yêu cầu phản biện:
- ROI có quá đẹp không (phóng đại)?
- ROI có quá xấu không (bảo thủ quá đà)?
- Bảng nhạy cảm có lộ ra ngưỡng sống/chết nào không?
```

---

## Iterate — đẩy AI sâu hơn khi bản nháp chưa đủ

### Khi ROI > 20:1 (đẹp đáng nghi)

```text
ROI nhóm tôi = 25:1 — vượt ngưỡng 20:1.

Nhiều khả năng phóng đại. Kiểm tra:

1. Tỷ lệ sử dụng: > 80%? Có dữ liệu cứng hay chỉ giả định?
2. Chất lượng: > 85%? Có dữ liệu thử thực tế hay tham khảo?
3. Thời gian tiết kiệm thực > 80% thô? Đã trừ kiểm tra + đổi tab + làm
   lại?
4. Có quên phần chi phí nào không? Người kiểm tra thường là phần lớn.
5. Khối lượng/tháng: tính cho nhóm thử nghiệm hay toàn đội?

Tính lại với điều chỉnh:
- Tỷ lệ sử dụng: tối đa 70% (bảo thủ cho thử nghiệm bắt buộc).
- Chất lượng: tối đa 80% (bảo thủ cho viết nháp).
- Thời gian tiết kiệm thực = 50% thô (mức điển hình).
- Cộng đủ chi phí người kiểm tra ($X/việc).

ROI sau điều chỉnh: ___:1.

Nếu vẫn > 10:1 → có thể đúng. Nếu rơi xuống 2–5:1 → điều chỉnh đúng,
giả định cũ quá lạc quan.
```

### Khi ROI < 1:1

```text
ROI nhóm tôi = 0,7:1 < 1 → ở kịch bản cơ bản không khả thi.

Trước khi NO-GO, thử 3 hướng:
- Giảm chi phí: đổi mô hình rẻ hơn (50–80% giảm), bỏ công cụ không cần,
  đàm phán lại ràng buộc kiểm tra.
- Tăng giá trị: mở rộng thử nghiệm để rải triển khai, đào tạo tăng tỷ lệ
  sử dụng, tinh chỉnh câu lệnh tăng chất lượng.
- Đổi cách rải chi phí: rải triển khai cho 1 năm thay vì 90 ngày, đàm
  phán bậc doanh nghiệp với nhà cung cấp.

Tính ROI sau mỗi tổ hợp, đề xuất tổ hợp khả thi nhất.
```

---

## Trước khi dán kết quả vào worksheet — nhóm tự rà soát

- Công thức đúng: ROI = Giá trị/Chi phí (không phải tỷ suất lợi nhuận)?
- Tỷ lệ rơi vào tầng nào, xu hướng verdict là gì?
- Nếu > 20:1, đã kiểm tra giả định chưa?
- Nếu < 1:1, đã thử các hướng tăng chưa, mới quyết NO-GO?
- Điểm hoà vốn về tỷ lệ sử dụng và chất lượng có cho thấy ngưỡng sống/chết không?

---

## Câu hỏi mở rộng (chỉ làm khi còn thời gian)

```text
Sau khi tính ROI, suy nghĩ 3 góc chiến lược:

1. Thời gian: ROI 2:1 ở tháng đầu — sau 3 tháng / 1 năm / 3 năm thế nào?
   - Chi phí triển khai rải hết → chi phí giảm.
   - Tỷ lệ sử dụng tăng → giá trị tăng.
   - Giá nhà cung cấp giảm → chi phí giảm.
   - ROI dài hạn thường > ROI tháng đầu.

2. Giá trị tích luỹ theo thời gian:
   - AI học từ dữ liệu dùng → chất lượng tăng (vòng dữ liệu).
   - Kỹ năng người dùng AI tăng → tỷ lệ sử dụng tăng, lỗi giảm.
   - 1 năm sau ROI có thể × 2 so với cơ bản.

3. Giá trị tuỳ chọn (optionality):
   - Thử nghiệm AI là một lựa chọn mở: nếu thành công → mở rộng; nếu
     thất bại → dừng.
   - Chi phí của việc KHÔNG thử = đối thủ làm trước.
   - ROI 1,5:1 vẫn có thể bảo vệ được nếu giá trị tuỳ chọn cao.

3 góc này giúp đề bài có lập luận đầy đủ cho người mua — không chỉ "ROI
tháng nào".
```
