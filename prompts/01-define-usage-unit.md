# Câu lệnh AI 1 — Định nghĩa đơn vị AI làm việc

**Dùng khi**: Bước 1 của Lab — sau khi đọc đề bài, nhóm cần xác định "AI làm việc gì trong một lần chạy" (gọi là *Usage Unit*) trước khi tính bất kỳ chi phí nào.

**Công cụ gợi ý**: Claude, ChatGPT, Gemini.

**Lưu kết quả vào**: `worksheet/01-cost-model/1-usage-unit.md`, Phần A và Phần C.

**Thời gian**: 10–15 phút.

---

## Trước khi vào câu lệnh — 5 câu nhóm tự trả lời

Đây không phải để dán vào AI. Đây là để nhóm tự hỏi nhau trước, để khi đọc bản nháp AI sinh ra, nhóm biết cái nào hợp lý cái nào không. AI sẽ "đoán" nếu nhóm chưa định hình — đoán sai thì cả Cost Model sau đó lệch theo.

1. Đề bài thuộc ngành nào, đội nào, làm việc gì cụ thể?
2. Đọc lại quy trình (trường 2 của đề bài): AI chen vào ở khâu nào trong quy trình?
3. Đọc lại ràng buộc (trường 5): có bắt buộc 100% người kiểm tra không? Có cấm AI tự gửi không?
4. AI thay vai trò ai trong khâu đó — tự làm thay người, hay chỉ hỗ trợ người ra quyết định?
5. Đầu ra một lần AI chạy trông như thế nào — một nhãn phân loại, một đoạn văn, một quyết định, hay một bảng dữ liệu?

Trả lời 5 câu này xong, cả nhóm sẽ thống nhất được "AI làm gì" trước khi để AI gợi ý.

---

## Câu lệnh chính (dán sau `00-context.md`)

```text
Bạn là Product Manager AI có kinh nghiệm tính kinh tế cho sản phẩm AI.
Dựa trên bối cảnh ở trên (`00-context.md` + đề bài đã giao), giúp nhóm tôi
định nghĩa đơn vị AI làm việc (Usage Unit) cho sản phẩm AI trong đề bài.

Usage Unit = đơn vị nguyên tử kinh tế của sản phẩm AI = "AI làm gì trong
một lần chạy".

Yêu cầu:

1. Đề xuất 3 phương án Usage Unit cho đề bài, mỗi phương án gồm:
   - Tên ngắn (vd: "1 bản nháp trả lời ticket", "1 lần gắn cờ kiểm duyệt")
   - Mô tả 2–3 câu (đầu vào là gì, đầu ra là gì, đầu ra đi đâu)
   - AI chạy khi nào (người bấm nút / tự động theo sự kiện / theo lịch)
   - Qua 3 câu kiểm tra:
     a. Đếm được không? (đếm "AI đã làm việc này X lần" mà không tranh cãi)
     b. Có tốn token không? (mỗi lần chạy có gọi API thật, có chi phí thật)
     c. Người dùng có thấy giá trị không? (rút ngắn thời gian hoặc cải
        thiện chất lượng cho một người dùng cụ thể)

2. Đánh giá 3 phương án theo 4 tiêu chí, chấm 1–5:
   - Đơn vị nhỏ nhất (atomic): có phải đúng "một lần AI chạy", hay là
     gom nhiều lần?
   - Đếm được trong thực tế (countable): khi triển khai có log lại được?
   - Gắn với chi phí (cost-linked): từ đơn vị này có dễ tính chi phí mỗi
     lần chạy không?
   - Gắn với giá trị (value-linked): từ đơn vị này có dễ tính giá trị mỗi
     lần chạy không?

3. Đề xuất phương án nên chọn + 2–3 câu lý do.

4. Cảnh báo các lỗi hay mắc cho đề bài này:
   - Quá rộng (vd: "AI hỗ trợ team support")
   - Quá hẹp (vd: "1 token AI sinh ra")
   - Không phải đơn vị nhỏ nhất (1 đơn vị gọi AI nhiều lần)
   - Đúng kỹ thuật nhưng sai góc nhìn kinh doanh (vd: "1 lần gọi API")

Yêu cầu phản biện:
- Nếu đề bài có ràng buộc 100% người kiểm tra, Usage Unit nên là "1 lần
  AI chạy" hay "1 lần AI + người kiểm tra gộp lại"?
- Nếu quy trình có nhiều bước (vd: tìm tài liệu + viết nháp + sửa = 3
  lần AI chạy), đếm là 1 đơn vị hay 3 đơn vị?
- Nếu người dùng có thể bấm "thử lại" / "tạo lại", đếm 1 lần thử hay
  1 kết quả cuối?

Yêu cầu trình bày:
- Viết tiếng Việt thoát nghĩa, không dịch nửa vời.
- Trình bày 3 phương án theo cùng định dạng.
- Đề xuất cuối ngắn gọn 2–3 câu.
```

---

## Iterate — đẩy AI sâu hơn khi bản nháp chưa đủ

### Khi AI đưa ra phương án quá rộng (vd: "1 ticket được giải quyết")

```text
Phương án bạn đề xuất ("1 ticket được giải quyết") là kết quả cuối, không
phải một lần AI chạy. Một ticket thường gọi AI nhiều lần: 1 lần tìm tài
liệu, 1 lần viết nháp, có khi 1 lần sửa lại.

Đề xuất lại: Usage Unit nên là 1 trong các bước AI gọi cụ thể, hay là
"1 bản nháp trả lời ticket" (= bước viết nháp, bước có giá trị rõ nhất
với người dùng)?

Nếu chọn "1 bản nháp trả lời", thì bước "tìm tài liệu" tính vào đâu —
gộp vào chi phí của bước viết nháp, hay tách thành đơn vị phụ riêng?
Cái nào dễ đo và dễ tính tiền hơn trong thực tế?
```

### Khi AI đưa ra phương án quá kỹ thuật (vd: "1 lần gọi API")

```text
Phương án bạn đề xuất là đúng kỹ thuật nhưng sai góc nhìn kinh doanh.

Vấn đề:
- Người mua (giám đốc kỹ thuật, phó tổng) không hiểu "1 lần gọi API"
  nghĩa là gì, vì sao họ trả tiền cho nó.
- Người dùng không trả tiền theo "số lần gọi API" — họ trả tiền theo
  việc cụ thể đã làm được.

Đề xuất lại Usage Unit ở tầng giữa:
- Không quá kỹ thuật (như "1 token")
- Không quá rộng (như "1 ticket được giải quyết")
- Ở giữa: "một việc AI làm mà người mua sẵn sàng trả tiền cho" — vd: 1
  bản nháp, 1 lần gắn cờ, 1 dự báo, 1 lần kiểm tra hợp đồng.

Tìm tầng giữa cho đề bài này, đề xuất 2 phương án cụ thể.
```

### Khi nhóm muốn đối chiếu với sản phẩm thật

```text
Tìm 2 sản phẩm AI tương tự (cùng ngành hoặc cùng mô hình hoạt động) và
xem họ định nghĩa Usage Unit như thế nào:

1. Sản phẩm: ___
   - Họ tính tiền theo đơn vị gì?
   - URL trang giá: ___
   - Có giống phương án nhóm tôi đề xuất không?

2. Sản phẩm: ___
   - (như trên)

Sau khi tham khảo, có nên sửa lại Usage Unit cho đề bài của nhóm tôi
không, sửa thế nào?
```

---

## Trước khi dán kết quả vào worksheet — nhóm tự rà soát

- Phương án chọn có qua cả 3 câu kiểm tra không (đếm được, tốn token, có giá trị)?
- Có thực sự là đơn vị nhỏ nhất, hay là kết quả gộp nhiều lần AI chạy?
- Người mua (giám đốc kỹ thuật, phó tổng) có hiểu được Usage Unit này và có thể bảo vệ trong cuộc họp duyệt ngân sách không?

Nếu một câu trả lời "không" — quay lại sửa trước khi dán vào worksheet.

---

## Câu hỏi mở rộng (chỉ làm khi còn thời gian)

```text
Sau khi chọn Usage Unit, giúp tôi nghĩ thêm 3 tình huống dài hạn:

1. Nếu đề bài tăng quy mô gấp 10 lần (vd: 5 nhân viên → 50 nhân viên),
   Usage Unit này có chịu được không?
   - Khối lượng × 10 có gây vấn đề gì (giới hạn API, dung lượng vector DB)?

2. Nếu nhà cung cấp AI ngừng mô hình hiện tại, Usage Unit có cần định
   nghĩa lại không?
   - Vd: mô hình mới có cửa sổ ngữ cảnh khác → số token đổi → chi phí
     mỗi lần chạy đổi.

3. Nếu có quy định bắt buộc chạy nội bộ (on-premise), Usage Unit có khả
   thi không?
   - Mô hình nội bộ thường tính tiền theo giờ GPU, không theo token.

3 câu này giúp nhóm thấy Usage Unit không chỉ đúng ở quy mô thử nghiệm
mà còn đứng vững khi quy mô thay đổi — quan trọng cho phần verdict ở Bước 3.
```
