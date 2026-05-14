# Câu lệnh AI 2 — Tra giá và tính công thức chi phí

**Dùng khi**: Bước 1 Lab, sau khi nhóm đã chốt Usage Unit, cần tra giá nhà cung cấp AI thật và tính chi phí mỗi tháng cho nhóm thử nghiệm.

**Công cụ gợi ý**: Claude, ChatGPT (có duyệt web), Perplexity.

**Lưu kết quả vào**: `worksheet/01-cost-model/2-cost-research.md` + phần A.7 trong `3-FINAL-cost-model.md`.

**Thời gian**: 15–20 phút.

---

## Trước khi vào câu lệnh — 5 câu nhóm tự trả lời

AI rất hay "bịa" giá tiền, đặc biệt với mô hình mới hoặc mô hình vừa ngừng. Trả lời 5 câu này trước để nhóm có khung kiểm tra khi đọc bản nháp AI sinh ra.

1. Usage Unit đã chốt là gì (lấy từ `1-usage-unit.md`)?
2. Đã có ước lượng số token đầu vào và đầu ra cho một lần chạy chưa?
3. Nhóm dự định dùng nhà cung cấp nào (OpenAI / Anthropic / Google / Azure / mã nguồn mở)?
4. Có cần các công cụ phụ không — vector DB (lưu tài liệu để tìm), công cụ giám sát, công cụ ghép quy trình?
5. Đề bài có ràng buộc người kiểm tra không — nếu có, mỗi lần kiểm tra mất bao nhiêu phút?

Quy tắc cứng: **mỗi giá tiền AI đưa ra đều phải có URL trang giá kèm theo**. Không có URL = không nhận số.

---

## Câu lệnh chính (dán sau `00-context.md` và Usage Unit đã chốt)

```text
Bạn là Product Manager AI có kinh nghiệm tính chi phí cho sản phẩm AI.
Dựa trên bối cảnh ở trên (`00-context.md` + Usage Unit đã định nghĩa),
giúp nhóm tôi tra giá và tính chi phí mỗi tháng cho đề bài.

Điều kiện trước: Usage Unit đã rõ. Tôi muốn tính chi phí đầy đủ từ A đến Z.

Phần 1 — Tra giá:
Đề xuất 3 mô hình phù hợp với Usage Unit:
- Mô hình A (rẻ): tên + $/1M token đầu vào + $/1M token đầu ra + URL
- Mô hình B (trung cấp): (như trên)
- Mô hình C (cao cấp): (như trên)

Sau đó đề xuất mô hình nào cho đề bài của tôi, kèm lý do (chất lượng,
giá, tốc độ phản hồi). Nếu chọn sai, chi phí sẽ lệch bao nhiêu?

Quy tắc cứng: nếu bạn không chắc chắn về một con số, ghi rõ "chưa kiểm
tra — cần mở URL xác nhận". Không bịa số.

Phần 2 — Ước lượng số token:
Cho Usage Unit của tôi, ước lượng:
- Token đầu vào (câu lệnh + ngữ cảnh + hướng dẫn hệ thống): ___ token
- Token đầu ra (phản hồi AI): ___ token
- Nếu có nhiều bước: cộng dồn token cả các bước.

Sau đó tính chi phí mỗi lần chạy = (token đầu vào × giá đầu vào + token
đầu ra × giá đầu ra) / 1.000.000.

Phần 3 — Chi phí công cụ phụ:
Đề bài có cần các công cụ sau không? Nếu có, ước lượng giá/tháng + URL:
- Vector DB (cho tìm tài liệu): cần / không cần
- Giám sát (Langfuse, Helicone): cần / không cần
- Ghép quy trình (n8n, LangChain): cần / không cần
- API tạo embedding (nếu có tìm tài liệu): cần / không cần

Phần 4 — Chi phí người kiểm tra:
Nếu đề bài có ràng buộc người kiểm tra:
- Tiền công mỗi giờ (đã cộng phụ phí): $___/giờ (= cơ bản × 1.3–1.5)
- Thời gian kiểm tra một việc: ___ phút (lấy từ đề bài hoặc giả định)
- Chi phí mỗi lần kiểm tra = (phút / 60) × tiền công/giờ
- Chi phí kiểm tra mỗi tháng = khối lượng tháng × chi phí mỗi lần.

Phần 5 — Chi phí triển khai ban đầu (rải đều):
Ước lượng tiền triển khai 1 lần ($):
- Tích hợp: ___ kỹ sư × ___ tuần × $___/tuần
- Kiểm tra bảo mật: ___
- Tinh chỉnh câu lệnh: ___
- Đào tạo người dùng: ___

Rải đều cho thời gian thử nghiệm → chi phí triển khai/tháng.

Phần 6 — Công thức chi phí mỗi tháng:
Tổng hợp:
Chi phí/tháng = (khối lượng × chi phí mỗi lần chạy)
              + chi phí công cụ
              + (khối lượng × chi phí kiểm tra)
              + chi phí triển khai rải đều
            = $___/tháng

Phần 7 — So với ngân sách:
Tổng chi phí so với ngân sách đề bài là bao nhiêu phần trăm? Nếu vượt
ngân sách, đề xuất hành động cụ thể.

Yêu cầu trình bày:
- Mỗi giá tiền có URL nguồn.
- Mỗi giả định (số token, thời gian kiểm tra) có lý do 1 câu.
- Viết tiếng Việt thoát nghĩa.

Yêu cầu phản biện:
- Mô hình giá nào dễ "bùng" khi khối lượng tăng mạnh (vd: tính theo
  token mà ngữ cảnh dài)?
- Có chi phí ẩn nào nhóm tôi đang quên không?
- Chi phí mỗi lần chạy có hợp lý so với mức tham khảo của ngành không?
```

---

## Iterate — đẩy AI sâu hơn khi bản nháp chưa đủ

### Khi giá AI đưa ra có vẻ bịa hoặc URL không mở được

```text
Giá bạn đưa cho Mô hình X ($___/1M token) — URL không mở được, hoặc
trang giá không khớp với số bạn nói.

Kiểm tra lại:
1. Mở trực tiếp trang giá chính thức (openai.com/api/pricing,
   anthropic.com/pricing, cloud.google.com/vertex-ai/pricing).
2. Ghi rõ "tính đến ngày [ngày kiểm tra]" — giá đổi rất thường.
3. Nếu giá có nhiều bậc theo khối lượng, ghi rõ nhóm tôi rơi vào bậc nào.
4. Nếu nhà cung cấp có chiết khấu doanh nghiệp (cần hợp đồng), ghi rõ
   "giá niêm yết, doanh nghiệp có thể thương lượng giảm ___%".

Không đưa số nếu không có URL mở được.
```

### Khi nhóm muốn so sánh 2–3 mô hình cùng lúc

```text
Tính chi phí cho 3 mô hình ở quy mô thử nghiệm (khối lượng = ___ việc/tháng):

| Mô hình | Chi phí/lần chạy | Chi phí API/tháng | % ngân sách |
|---|---|---|---|
| Rẻ | $___ | $___ | ___% |
| Trung | $___ | $___ | ___% |
| Cao cấp | $___ | $___ | ___% |

Đề xuất mô hình phù hợp dựa trên:
- Còn dư ngân sách (chi phí < 50% ngân sách = an toàn)
- Chất lượng cần thiết cho Usage Unit
- Tốc độ phản hồi cần thiết (mô hình lớn thường chậm hơn)

Nếu mô hình rẻ đủ chất lượng → chọn rẻ. Không mặc định chọn cao cấp.
```

### Khi muốn xem phần nào chiếm chi phí nhiều nhất

```text
Tổng chi phí/tháng = $___. Phân tích theo từng phần:

| Phần | $/tháng | % |
|---|---|---|
| Chi phí API | $___ | ___% |
| Công cụ phụ | $___ | ___% |
| Người kiểm tra | $___ | ___% |
| Triển khai (rải đều) | $___ | ___% |

- Phần nào chiếm > 50%? Đó là chỗ cần tối ưu trước.
- Phần nào < 5%? Không cần tập trung.
- Phần nào bất ngờ (cao hoặc thấp ngoài dự đoán)?
```

---

## Trước khi dán kết quả vào worksheet — nhóm tự rà soát

- Mỗi giá tiền có URL trang giá mở được không?
- Số token ước lượng có hợp lý cho Usage Unit của nhóm không?
- Có quên chi phí người kiểm tra / triển khai / giám sát không?
- Tổng chi phí có trong ngân sách của đề bài không? Nếu vượt, có hành động cụ thể chưa?

---

## Câu hỏi mở rộng (chỉ làm khi còn thời gian)

```text
Sau khi tính chi phí, nhìn thêm 3 góc:

1. Nếu khối lượng tăng 5 lần (mở rộng từ nhóm thử nghiệm ra toàn đội),
   phần nào tăng tuyến tính, phần nào "nhảy bậc" (vd: vượt bậc doanh
   nghiệp, gói công cụ miễn phí hết hạn)?

2. Ngoài nhà cung cấp chính, có lựa chọn nào rẻ hơn 50% trở lên không?
   - Mã nguồn mở qua Replicate / Together AI?
   - Tự host (cần GPU)?
   - Đánh đổi gì (chất lượng, tốc độ, hỗ trợ)?

3. Cách tối ưu chi phí:
   - Lưu lại kết quả AI cho đầu vào lặp lại → giảm bao nhiêu %?
   - Mô hình nhỏ cho việc dễ, mô hình lớn cho việc khó (chia tầng)?
   - Xử lý theo lô thay vì thời gian thực?

3 câu này chuẩn bị cho Bước 3 — kịch bản nhà cung cấp đổi giá.
```
