# Bộ đề bài — Ngày 27 Lab

Mỗi cặp nhận **một** đề bài trong danh sách dưới đây. Đề bài chứa toàn bộ ngữ cảnh kinh tế nhóm cần để dựng bảng AI Economics Sheet (Chi phí → Định giá → Giá trị → Stress test → Quyết định cuối).

**Quy tắc dùng đề bài**:

- Đọc kỹ cả 9 trường trước khi tính bất kỳ con số nào.
- Mọi số liệu trong Economics Sheet phải truy ngược về đề bài hoặc về trang giá của nhà cung cấp AI mà nhóm tự tra.
- Nếu thấy ngữ cảnh quá lạ với cả nhóm, giảng viên có thể cho phép đổi đề bài — nhưng phải báo trước 10:10.

**Đề bài #1 (AI Support Copilot)** được viết chi tiết nhất để làm ví dụ mẫu — các đề bài sau viết cô đọng hơn nhưng vẫn đủ 9 trường.

---

## Đề bài #1 — AI Support Copilot

> **Ngành**: B2B SaaS — hỗ trợ khách hàng
> **Kiểu thử nghiệm**: AI hỗ trợ nhân viên (copilot), không tự gửi mail

### 1. Bối cảnh doanh nghiệp

Công ty SaaS B2B, 200 nhân viên, ~15,000 khách hàng doanh nghiệp đang trả phí. Đội hỗ trợ khách hàng có 25 agent, xử lý khoảng 800 ticket mỗi ngày. CSAT hiện ở mức 72%, mục tiêu CEO đặt ra cho năm là 85%. Tỷ lệ churn (khách rời dịch vụ) liên quan đến trải nghiệm hỗ trợ kém: 18% (theo khảo sát rời dịch vụ — exit survey — Q1).

### 2. Quy trình hiện tại

Ticket đến → vào hàng đợi Zendesk → agent đọc → tra cứu tài liệu trong knowledge base (KB) → tự viết câu trả lời → agent senior duyệt lại → gửi cho khách. Thời gian xử lý trung bình: 12 phút/ticket. Thời gian phản hồi đầu: 4 giờ.

### 3. Điểm đau

- 40% thời gian của agent dành cho việc tra cứu trong KB.
- KB lỗi thời 30% — lần rà soát toàn bộ gần nhất cách đây 8 tháng.
- Câu hỏi FAQ tier-1 chiếm 45% tổng lượng ticket.
- Agent mới mất 3 tuần để đạt năng suất chuẩn.

### 4. Dữ liệu sẵn có

- 50,000 ticket đã giải quyết kèm rating của khách (2 năm gần đây).
- 800 bài KB + tài liệu nội bộ.
- CSAT theo từng ticket.

### 5. Ràng buộc

- KHÔNG được tự động gửi (auto-send) cho khách hàng (ràng buộc tuân thủ pháp lý).
- PII (Personal Identifiable Information — thông tin định danh cá nhân) phải được che (mask) trước khi đưa vào AI.
- Cần phê duyệt của bộ phận an ninh thông tin (quy trình 2 tuần).

### 6. Quyết định cần đưa ra

CTO hỏi: "Có nên xây AI copilot hỗ trợ agent viết bản nháp trả lời, hay xây bộ tự động trả lời (auto-responder) xử lý FAQ tier-1?"

### 7. Chỉ số nền

- Thời gian xử lý: 12 phút/ticket.
- Thời gian phản hồi đầu: 4 giờ.
- CSAT: 72%.

### 8. Ngân sách & thời gian pilot

- Ngân sách: $5,000/tháng.
- Thời gian: 90 ngày.
- Phạm vi: 5 agent (trong tổng 25).

### 9. Ranh giới rủi ro

- Gợi ý sai chính sách → vi phạm tuân thủ.
- Tự động trả lời sai → mất niềm tin của khách.
- Agent lệ thuộc AI quá mức → kỹ năng suy giảm.

---

## Đề bài #2 — AI Content Moderator

> **Ngành**: Mạng xã hội — kiểm duyệt nội dung (Trust & Safety)
> **Kiểu thử nghiệm**: AI lọc trước (pre-filter), người vẫn duyệt 100%

### 1. Bối cảnh doanh nghiệp

Nền tảng mạng xã hội với 2 triệu bài đăng mỗi ngày. Đội Trust & Safety: 15 người duyệt nội dung (reviewer).

### 2. Quy trình hiện tại

Reviewer phải duyệt thủ công 20,000 báo cáo (flag) mỗi ngày — gồm cả flag do người dùng báo cáo và flag do hệ thống tự phát hiện. Mỗi flag mất khoảng 5 phút để đọc, đối chiếu chính sách, ra quyết định.

### 3. Điểm đau

- Tồn đọng 6 giờ — nội dung nguy hiểm tồn tại trên nền tảng lâu trước khi bị gỡ.
- 3% nội dung có hại nằm trên nền tảng hơn 4 giờ trước khi bị xử lý.
- Reviewer kiệt sức vì phải xem nội dung độc trong nhiều giờ liền.

### 4. Dữ liệu sẵn có

- 5 triệu flag đã được phân loại trong 12 tháng qua, có nhãn rõ ràng.
- Chính sách nội bộ dài 80 trang, chia 5 nhóm chính.

### 5. Ràng buộc

- 100% quyết định gỡ bài phải có người duyệt (ràng buộc tuân thủ pháp lý).
- AI chỉ được lọc trước và xếp ưu tiên, không tự gỡ.
- Phải lưu nhật ký kiểm toán (audit trail) cho mỗi quyết định.

### 6. Quyết định cần đưa ra

VP Trust & Safety hỏi: "AI lọc trước cho 5 nhóm nội dung có giúp giảm tồn đọng từ 6 giờ xuống dưới 2 giờ không, đồng thời giữ chất lượng duyệt?"

### 7. Chỉ số nền

- Tồn đọng hiện tại: 6 giờ.
- Mục tiêu: dưới 2 giờ.
- Tỷ lệ bỏ sót nội dung độc (false negative): 3%.

### 8. Ngân sách & thời gian pilot

- Ngân sách: $8,000/tháng.
- Thời gian: 60 ngày.
- Phạm vi: 5 reviewer (trên 15).

### 9. Ranh giới rủi ro

- AI bỏ sót nội dung nguy hiểm (false negative) → tổn thương người dùng, rủi ro pháp lý.
- AI gắn nhầm nội dung lành (false positive) → reviewer tốn thời gian xử lý nhiễu.
- Sai sót lan rộng do khối lượng cao (146K flag/tháng pilot) → cần giám sát chặt.

---

## Đề bài #3 — AI Medical Triage Assistant

> **Ngành**: Bệnh viện — khoa Cấp cứu (ER)
> **Kiểu thử nghiệm**: AI đánh giá trước, y tá luôn quyết định cuối

### 1. Bối cảnh doanh nghiệp

Bệnh viện đa khoa, khoa Cấp cứu (ER) tiếp nhận 300 bệnh nhân/ngày. Đội phân loại (triage) có 8 y tá, mỗi ca làm việc khoảng 6 y tá.

### 2. Quy trình hiện tại

Y tá phỏng vấn bệnh nhân khi tiếp nhận → chấm điểm bằng thang ESI (Emergency Severity Index — thang mức độ khẩn cấp) thủ công → xếp ưu tiên. Thời gian trung bình: 8 phút/bệnh nhân.

### 3. Điểm đau

- Thời gian chờ phân loại trung bình 15 phút, nhiều ca cấp cứu nặng chờ quá lâu.
- 12% bệnh nhân bị xếp sai mức ban đầu (phải phân loại lại).
- Thời điểm cao điểm: 1 y tá xử lý 2-3 bệnh nhân cùng lúc, dễ sai sót.

### 4. Dữ liệu sẵn có

- 200,000 hồ sơ phân loại trong 3 năm (mẫu tiếp nhận + điểm ESI + kết quả thực tế).
- Quy trình ESI chuẩn của bệnh viện (60 trang).

### 5. Ràng buộc

- Y tá LUÔN là người ra quyết định phân loại cuối — AI chỉ gợi ý.
- Tuân thủ HIPAA (Mỹ) hoặc tương đương về bảo mật bệnh nhân.
- Không được trì hoãn quy trình phân loại hiện tại — AI phải chạy dưới 30 giây.

### 6. Quyết định cần đưa ra

Trưởng khoa hỏi: "AI đánh giá trước từ mẫu tiếp nhận có giảm thời gian chờ xuống dưới 8 phút và giảm tỷ lệ phân loại sai xuống dưới 5%?"

### 7. Chỉ số nền

- Thời gian phân loại: 8 phút/bệnh nhân.
- Thời gian chờ: 15 phút.
- Tỷ lệ phân loại sai: 12%.

### 8. Ngân sách & thời gian pilot

- Ngân sách: $3,000/tháng.
- Thời gian: 90 ngày.
- Phạm vi: 3 y tá (trong 8).

### 9. Ranh giới rủi ro

- AI gợi ý sai mức phân loại → bệnh nhân nặng chờ lâu, có thể tử vong.
- Y tá quá tin AI → bỏ qua tín hiệu thực tế.
- Rò rỉ dữ liệu tiếp nhận → vi phạm pháp lý nghiêm trọng.

---

## Đề bài #4 — AI Legal Contract Reviewer

> **Ngành**: Văn phòng luật M&A
> **Kiểu thử nghiệm**: AI làm nổi bật điều khoản bất thường, luật sư kiểm chứng

### 1. Bối cảnh doanh nghiệp

Văn phòng luật chuyên M&A, đội 8 luật sư xử lý 200 hợp đồng/tháng. Phần lớn là MSA (Master Service Agreement — hợp đồng khung dịch vụ), NDA (thỏa thuận bảo mật), share purchase agreement (hợp đồng mua bán cổ phần).

### 2. Quy trình hiện tại

Luật sư junior đọc toàn bộ hợp đồng → đánh dấu các điều khoản cần lưu ý → tạo danh sách vấn đề → luật sư senior duyệt lại. Trung bình 3 giờ/hợp đồng cho junior, 1 giờ cho senior.

### 3. Điểm đau

- Luật sư junior dành 60% thời gian cho phần duyệt thường lệ (điều khoản mẫu — boilerplate) → không học được gì mới.
- Bỏ sót điểm tinh tế trong các điều khoản phức tạp (ví dụ: bồi thường thiệt hại, chuyển giao IP) → phát hiện muộn ở giai đoạn đàm phán.
- Tốc độ duyệt chậm so với hạn của khách hàng.

### 4. Dữ liệu sẵn có

- 5,000 hợp đồng M&A đã duyệt trong 5 năm, có danh sách vấn đề đính kèm.
- Sổ tay nội bộ (playbook): 200 điều khoản chuẩn + 50 điều khoản cảnh báo (red flag).

### 5. Ràng buộc

- Mọi điều khoản AI đánh dấu phải có luật sư kiểm chứng trước khi đưa vào danh sách vấn đề chính thức.
- Hợp đồng có thể chứa thông tin đặc quyền khách hàng (client-privileged) — không gửi ra cloud công cộng.
- Phải có nhật ký kiểm toán cho mỗi gợi ý AI.

### 6. Quyết định cần đưa ra

Managing partner hỏi: "AI đánh dấu điều khoản phi tiêu chuẩn có rút thời gian duyệt xuống 40% và tăng độ chính xác phát hiện red flag không?"

### 7. Chỉ số nền

- Thời gian duyệt của junior: 3 giờ/hợp đồng.
- Tổng thời gian một vòng: 4 giờ (junior + senior).
- Tỷ lệ bỏ sót red flag: ~8% (theo hồi cứu 6 tháng qua).

### 8. Ngân sách & thời gian pilot

- Ngân sách: $10,000/tháng.
- Thời gian: 60 ngày.
- Phạm vi: 3 luật sư (1 senior + 2 junior).

### 9. Ranh giới rủi ro

- AI bỏ sót điều khoản nguy hiểm → khách hàng chịu rủi ro pháp lý lớn.
- AI đánh dấu nhầm quá nhiều → luật sư mất thời gian sàng lọc.
- Rò rỉ dữ liệu hợp đồng → vi phạm đặc quyền luật sư - khách hàng.

---

## Đề bài #5 — AI Sales Email Generator

> **Ngành**: Bán hàng B2B trên nền tảng e-commerce
> **Kiểu thử nghiệm**: AI viết nháp email cá nhân hóa, SDR duyệt trước khi gửi

### 1. Bối cảnh doanh nghiệp

Công ty e-commerce nền tảng B2B, có 5,000 lead mới mỗi tuần. Đội SDR (Sales Development Rep — nhân viên phát triển khách hàng) 12 người.

### 2. Quy trình hiện tại

SDR đọc thông tin về prospect — khách hàng tiềm năng (LinkedIn + website công ty) → viết email cá nhân hóa → gửi → theo dõi nếu chưa có phản hồi. Trung bình 25 phút/lead.

### 3. Điểm đau

- Chỉ tiếp cận được 800 lead/tuần (16% lượng vào) — bỏ lỡ 4,200 lead/tuần.
- Tỷ lệ phản hồi 4% — không cao vì cá nhân hóa nông.
- SDR nói "nghiên cứu prospect" mất quá nhiều thời gian so với "thực sự bán hàng".

### 4. Dữ liệu sẵn có

- 80,000 email đã gửi trong 12 tháng + tỷ lệ mở/phản hồi/đặt lịch.
- Cơ sở dữ liệu 5,000 prospect/tuần với firmographic (đặc điểm công ty) + tech stack (bộ công nghệ đang dùng).

### 5. Ràng buộc

- SDR phải duyệt và phê duyệt email trước khi gửi (không tự động gửi).
- Email phải tuân thủ CAN-SPAM + GDPR — không spam danh sách lạnh chưa opt-in.
- Phải cá nhân hóa cụ thể (tên công ty + ngành + điểm đau) — không phải email gửi hàng loạt.

### 6. Quyết định cần đưa ra

VP Sales hỏi: "AI viết nháp email có giúp tăng lượng tiếp cận lên 60% (3,000 lead/tuần) và giữ tỷ lệ phản hồi ≥ 4%?"

### 7. Chỉ số nền

- Lượng tiếp cận: 800 lead/tuần (16%).
- Tỷ lệ phản hồi: 4%.
- Tỷ lệ đặt được lịch họp: 0.8%.

### 8. Ngân sách & thời gian pilot

- Ngân sách: $4,000/tháng.
- Thời gian: 90 ngày.
- Phạm vi: 4 SDR (trong 12).

### 9. Ranh giới rủi ro

- AI viết sai giọng thương hiệu → khách phản ánh tiêu cực.
- AI bịa thông tin về prospect → mất uy tín.
- Khiếu nại spam tăng → tên miền bị chặn, ảnh hưởng cả đội.

---

## Đề bài #6 — AI Code Review Assistant

> **Ngành**: Fintech — kỹ thuật phần mềm
> **Kiểu thử nghiệm**: AI duyệt sơ bộ pull request (PR), senior engineer phê duyệt cuối

### 1. Bối cảnh doanh nghiệp

Công ty fintech, đội kỹ thuật 40 người, phát hành 150 pull request (PR) mỗi ngày. Tuân thủ PCI-DSS + SOC 2 (chuẩn an toàn dữ liệu thẻ thanh toán + chuẩn kiểm soát dịch vụ).

### 2. Quy trình hiện tại

Engineer mở PR → senior engineer duyệt (an toàn bảo mật + phong cách code + độ phủ test) → bình luận → engineer sửa → gộp code. Trung bình 30 phút/PR cho senior, hàng đợi chờ trung bình 2 ngày.

### 3. Điểm đau

- Điểm nghẽn duyệt code làm chậm chu kỳ phát hành — phát hành chậm 3 ngày so với mục tiêu.
- 8% bug lọt qua duyệt (phát hiện ở môi trường staging hoặc production).
- Senior engineer phải duyệt nhiều PR đơn giản → ít thời gian cho thiết kế hệ thống.

### 4. Dữ liệu sẵn có

- 30,000 PR đã gộp + bình luận + kết quả (có bug / sạch) trong 2 năm.
- Chuẩn coding nội bộ (50 trang) + danh sách kiểm tra an toàn bảo mật (30 mục).

### 5. Ràng buộc

- Senior engineer LUÔN phê duyệt cuối — AI chỉ duyệt sơ bộ.
- Code không được tải lên cloud công cộng (code có thể chứa secret — khóa bí mật).
- AI phải chạy trong pipeline CI — không được làm chậm việc gộp quá 5 phút.

### 6. Quyết định cần đưa ra

VP Engineering hỏi: "AI duyệt sơ bộ có giảm hàng đợi duyệt từ 2 ngày xuống nửa ngày và giữ tỷ lệ bug lọt dưới 5%?"

### 7. Chỉ số nền

- Hàng đợi duyệt: 2 ngày.
- Thời gian duyệt: 30 phút/PR.
- Bug lọt: 8%.

### 8. Ngân sách & thời gian pilot

- Ngân sách: $6,000/tháng.
- Thời gian: 90 ngày.
- Phạm vi: 10 engineer (trong 40).

### 9. Ranh giới rủi ro

- AI bỏ sót lỗ hổng an toàn → rò rỉ dữ liệu fintech, chịu phạt PCI-DSS.
- AI đánh dấu sai (false positive) → engineer mất thời gian giải trình.
- Rò rỉ code → vi phạm sở hữu trí tuệ nội bộ.

---

## Đề bài #7 — AI Inventory Forecaster

> **Ngành**: Chuỗi bán lẻ — chuỗi cung ứng
> **Kiểu thử nghiệm**: AI dự báo hằng ngày, analyst phê duyệt đơn đặt lại

### 1. Bối cảnh doanh nghiệp

Chuỗi bán lẻ 50 cửa hàng, 500 SKU (mã sản phẩm) đang bán. Đội chuỗi cung ứng 5 analyst.

### 2. Quy trình hiện tại

Analyst chạy mô hình Excel (Excel + Moving Average + hệ số mùa vụ) hằng tuần → tạo dự báo cho 500 SKU → đề xuất đặt lại. Trung bình 2 ngày/tuần để tạo xong dự báo.

### 3. Điểm đau

- Sai số dự báo: 22% (cao so với chuẩn ngành 8-12%).
- $2 triệu/năm chi phí cho hàng tồn dư (overstock) và thiếu hàng (stockout).
- Dự báo hằng tuần → không kịp phản ứng với chương trình khuyến mãi, thời tiết, hoặc sự kiện đặc biệt.

### 4. Dữ liệu sẵn có

- 5 năm dữ liệu doanh số cho 500 SKU theo cửa hàng + ngày.
- Lịch khuyến mãi + dữ liệu thời tiết qua API + lịch ngày lễ.

### 5. Ràng buộc

- Analyst PHẢI phê duyệt mọi đề xuất đặt lại — AI chỉ gợi ý.
- Không kết nối trực tiếp với hệ thống ERP (Oracle) — đầu ra qua CSV/Excel để analyst kiểm tra.
- Phải giải thích được — analyst cần biết "vì sao AI gợi ý đặt lại 200 đơn vị?".

### 6. Quyết định cần đưa ra

Director Supply Chain hỏi: "AI dự báo hằng ngày cho top 100 SKU có giảm sai số dự báo xuống dưới 12% và giảm $2M chi phí xuống còn $1M?"

### 7. Chỉ số nền

- Sai số dự báo: 22%.
- Tổn thất mỗi năm (tồn dư + thiếu hàng): $2,000,000.
- Tần suất dự báo: theo tuần (mục tiêu: theo ngày).

### 8. Ngân sách & thời gian pilot

- Ngân sách: $5,000/tháng.
- Thời gian: 90 ngày.
- Phạm vi: 2 analyst, 100 SKU đầu (Top 100 theo doanh thu).

### 9. Ranh giới rủi ro

- AI dự báo thấp → thiếu hàng → mất doanh số.
- AI dự báo cao → tồn dư → ôm hàng + lãng phí (đặc biệt FMCG — hàng tiêu dùng nhanh).
- Đề xuất kiểu hộp đen → analyst không tin → không áp dụng.

---

## Đề bài #8 — AI Student Essay Grader

> **Ngành**: Đại học — chấm bài luận
> **Kiểu thử nghiệm**: AI chấm sơ bộ + viết nháp phản hồi, TA duyệt cuối

### 1. Bối cảnh doanh nghiệp

Đại học công lập, 3,000 bài luận/học kỳ trên 15 môn học khác nhau. Đội TA (Teaching Assistant — trợ giảng): 20 người, là sinh viên sau đại học làm bán thời gian.

### 2. Quy trình hiện tại

TA đọc từng bài luận → chấm điểm theo rubric (5 tiêu chí) → viết phản hồi 5-10 câu → trả bài. Trung bình 20 phút/bài.

### 3. Điểm đau

- Trả bài chậm 2 tuần — sinh viên đã sang môn sau khi chưa nhận phản hồi môn trước.
- Sai khác giữa các TA (cùng bài, TA khác chấm khác 1-2 điểm) — sinh viên khiếu nại.
- TA kiệt sức vì chấm bài nặng, ảnh hưởng nghiên cứu luận văn.

### 4. Dữ liệu sẵn có

- 30,000 bài luận đã chấm trong 5 năm + rubric chuẩn từng môn + phản hồi mẫu.

### 5. Ràng buộc

- TA duyệt từng điểm + phản hồi AI trước khi trả cho sinh viên (không tự động công bố).
- Điểm AI chỉ là gợi ý — TA có quyền điều chỉnh.
- Bài luận không được dùng để huấn luyện mô hình của bên thứ ba (FERPA + quyền riêng tư).

### 6. Quyết định cần đưa ra

Trưởng khoa hỏi: "AI chấm sơ bộ có rút thời gian trả bài xuống 3 ngày và giảm sai khác giữa các TA xuống dưới 0.5 điểm?"

### 7. Chỉ số nền

- Thời gian trả bài: 2 tuần.
- Thời gian chấm của TA: 20 phút/bài.
- Sai khác giữa các TA: ~1.5 điểm trên thang 10.

### 8. Ngân sách & thời gian pilot

- Ngân sách: $2,000/tháng.
- Thời gian: 1 học kỳ (15 tuần).
- Phạm vi: 5 TA, 3 môn học (~600 bài luận).

### 9. Ranh giới rủi ro

- AI thiên kiến khi chấm (ví dụ: ngôn ngữ không phải tiếng Anh bản ngữ bị chấm thấp) → ảnh hưởng công bằng học thuật.
- TA quá tin AI → không phát hiện được lỗi AI.
- Sinh viên phản đối "AI chấm bài" → khiếu nại lên ban giám hiệu.

---

## Đề bài #9 — AI Insurance Claim Processor

> **Ngành**: Bảo hiểm phi nhân thọ
> **Kiểu thử nghiệm**: AI xử lý sơ bộ giấy tờ + đối chiếu hợp đồng, adjuster phê duyệt

### 1. Bối cảnh doanh nghiệp

Công ty bảo hiểm phi nhân thọ, 1,000 claim (yêu cầu bồi thường) mỗi ngày — chủ yếu xe hơi + tài sản. Đội adjuster (định giá viên): 30 người.

### 2. Quy trình hiện tại

Adjuster nhận claim → duyệt hồ sơ (ảnh + giấy tờ + lời khai) → đối chiếu hợp đồng phù hợp → ước lượng thiệt hại → quyết định chi trả. Trung bình 45 phút/claim.

### 3. Điểm đau

- Thời gian xử lý claim trung bình 5 ngày — khách phàn nàn.
- 15% claim phải duyệt lại do thiếu thông tin hoặc đối chiếu hợp đồng sai.
- Adjuster mới mất 6 tháng để đạt năng suất chuẩn.

### 4. Dữ liệu sẵn có

- 500,000 claim đã xử lý trong 3 năm + kết quả (đã trả / từ chối / thương lượng).
- 200 mẫu hợp đồng + bảng đối chiếu điều khoản nội bộ.

### 5. Ràng buộc

- Adjuster PHẢI phê duyệt mọi quyết định claim — AI chỉ xử lý sơ bộ.
- Tuân thủ quy định ngành: NAIC (Mỹ) hoặc luật bảo hiểm địa phương.
- Tránh thiên kiến trong phê duyệt claim (đặc biệt: giới tính, sắc tộc, vùng địa lý).

### 6. Quyết định cần đưa ra

Director Claims hỏi: "AI xử lý sơ bộ có rút thời gian từ 5 ngày xuống 1.5 ngày và giảm tỷ lệ duyệt lại xuống dưới 5%?"

### 7. Chỉ số nền

- Thời gian xử lý: 5 ngày/claim.
- Công sức adjuster: 45 phút/claim.
- Tỷ lệ duyệt lại: 15%.

### 8. Ngân sách & thời gian pilot

- Ngân sách: $12,000/tháng.
- Thời gian: 90 ngày.
- Phạm vi: 8 adjuster (trong 30).

### 9. Ranh giới rủi ro

- AI đối chiếu sai hợp đồng → chi trả sai → gian lận hoặc thiệt hại cho công ty.
- AI thiên kiến → khách bị từ chối oan → kiện tụng + phạt quy định ngành.
- Rò rỉ giấy tờ claim → vi phạm PII của khách.

---

## Đề bài #10 — AI Real Estate Listing Generator

> **Ngành**: Đại lý bất động sản
> **Kiểu thử nghiệm**: AI tạo mô tả tin đăng + chú thích ảnh, agent duyệt lại

### 1. Bối cảnh doanh nghiệp

Đại lý bất động sản, 25 agent, đăng 200 tin đăng (listing) mới mỗi tháng (nhà ở + thương mại).

### 2. Quy trình hiện tại

Agent đến xem nhà → chụp 20-30 ảnh → viết mô tả (300-500 từ) → chú thích từng ảnh → đăng lên cổng (MLS / website công ty). Trung bình 90 phút/listing chỉ cho phần nội dung.

### 3. Điểm đau

- Chất lượng listing không đều — agent kinh nghiệm viết tốt, agent mới viết kém.
- 40% listing phải quản lý sửa lại trước khi công bố — chậm thời gian ra thị trường.
- Agent than phiền việc viết chiếm quá nhiều thời gian, ít gặp khách.

### 4. Dữ liệu sẵn có

- 8,000 listing đã đăng trong 4 năm + số liệu tương tác (lượt xem, lưu, liên hệ).
- Dữ liệu bất động sản: diện tích, năm xây, tiện ích, vị trí, các listing tương tự để so sánh.

### 5. Ràng buộc

- Agent duyệt + sửa mọi nội dung trước khi đăng — không tự động công bố.
- Tuân thủ Fair Housing Act (Mỹ — luật chống phân biệt đối xử trong bất động sản) hoặc tương đương — tránh ngôn ngữ phân biệt đối xử.
- Mô tả phải có yếu tố cá nhân hóa cho từng bất động sản (không phải mẫu chung chung).

### 6. Quyết định cần đưa ra

Broker-owner (chủ đại lý) hỏi: "AI tạo mô tả + chú thích có rút thời gian xuống 30 phút/listing và giảm tỷ lệ quản lý phải sửa xuống dưới 15%?"

### 7. Chỉ số nền

- Thời gian viết nội dung: 90 phút/listing.
- Tỷ lệ quản lý phải sửa: 40%.
- Tương tác (lượt xem trong tuần đầu): trung bình 250 lượt.

### 8. Ngân sách & thời gian pilot

- Ngân sách: $3,000/tháng.
- Thời gian: 60 ngày.
- Phạm vi: 8 agent (trong 25).

### 9. Ranh giới rủi ro

- AI bịa thông tin bất động sản (ví dụ: thêm tiện ích không có) → khách kiện tụng.
- Ngôn ngữ phân biệt đối xử (ví dụ: gợi ý "khu yên tĩnh, ít người da màu") → vi phạm Fair Housing.
- Nội dung chung chung → tương tác thấp → agent từ bỏ công cụ.

---

## Cách giảng viên phân đề bài

- Đề bài #1 — cặp đông kinh nghiệm B2B SaaS (làm chuẩn vì có ví dụ chi tiết nhất).
- Đề bài #2 — cặp quan tâm Trust & Safety / kiểm duyệt nội dung.
- Đề bài #3 — cặp có nền tảng y tế / healthtech.
- Đề bài #4 — cặp quan tâm legaltech / tuân thủ.
- Đề bài #5 — cặp có nền tảng bán hàng / marketing.
- Đề bài #6 — cặp là developer / có nền tảng kỹ thuật phần mềm.
- Đề bài #7 — cặp quan tâm vận hành / chuỗi cung ứng.
- Đề bài #8 — cặp có nền tảng giáo dục / nghiên cứu học thuật.
- Đề bài #9 — cặp có nền tảng bảo hiểm / fintech.
- Đề bài #10 — cặp có nền tảng bất động sản / marketing.

Mỗi đề bài đều có thể mở rộng để áp dụng cùng một khung phân tích — nền tảng ngành chỉ là điểm cộng, không bắt buộc.

---

## Ghi chú cho học viên

- Đề bài là **đầu vào cố định** — không tự ý thay đổi con số trong đề bài.
- Nếu thấy số liệu trong đề bài không khớp với thực tế ngành (ví dụ: SDR thực tế làm 35 phút/lead chứ không 25), được phép ghi chú trong worksheet: "Đề bài nói X, nhưng thực tế ngành là Y; nhóm dùng X để nhất quán."
- Mọi giả định mới (ví dụ: mô hình nào dùng, tỷ lệ sử dụng thực tế bao nhiêu) phải tự thêm vào worksheet và giải thích lý do.
