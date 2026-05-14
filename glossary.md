# Glossary — Ngày 27 (Kinh tế sản phẩm AI)

Bảng thuật ngữ Ngày 27. Cột trái giữ tên tiếng Anh (vì đa số tài liệu kinh tế sản phẩm AI ngoài thế giới dùng các từ này), cột giữa giải thích bằng tiếng Việt thoát nghĩa, cột phải là một ví dụ ngắn lấy từ chính Ngày 27.

Cách dùng: mở ra tra khi đọc worksheet / câu lệnh AI / slide bài giảng. Một số thuật ngữ học viên đã quen từ Ngày 25-26, một số mới xuất hiện ở Ngày 27.

---

## Khái niệm cốt lõi

| Thuật ngữ | Nghĩa | Ví dụ trong Ngày 27 |
|---|---|---|
| **Usage Unit** | Đơn vị nguyên tử của kinh tế sản phẩm AI — "AI làm việc gì trong một lần chạy". Phải qua 3 câu kiểm tra: đếm được, tốn token, có giá trị cho người dùng. | "1 bản nháp trả lời ticket" cho Đề bài #1; "1 lượt soi nội dung trước khi đăng" cho Đề bài #2 |
| **Cost-Capability-Speed Triangle** | Tam giác đánh đổi 3 chiều: rẻ / mạnh / nhanh. Mỗi quyết định sản phẩm AI rơi vào đâu đó trong tam giác — chọn tối ưu 2 thì phải hy sinh 1. | GitHub Copilot chia tầng: mô hình nhanh cho gợi ý code, mô hình mạnh cho phần chat sâu |
| **Monetization Triad** | Bộ ba phải khớp với nhau khi định giá AI: Giá trị cho khách + Vòng tăng trưởng + Chi phí làm ra doanh thu. Cách định giá phải đứng vững trên cả 3 trục. | Intercom Fin khớp cả 3: tính theo "1 vấn đề được giải quyết" = giá trị rõ + vòng tăng trưởng tự nhiên + chi phí biến đổi khớp doanh thu |
| **Value Metric Spectrum** | Phổ đơn vị tính tiền từ trừu tượng đến cụ thể: Seat → Usage → Outcome → Hybrid. Mỗi điểm có ưu nhược riêng. | Grammarly tính theo Seat (trừu tượng); OpenAI API tính theo Usage (cụ thể); Intercom Fin tính theo Outcome (cụ thể và gắn trực tiếp với giá trị) |
| **Attribution × Autonomy Matrix** | Ma trận 2×2 dùng để chọn cách định giá phù hợp: trục Autonomy (AI tự làm / chỉ hỗ trợ) × trục Attribution (AI là nguyên nhân rõ / khó tách công với người). | Autonomy thấp + Attribution thấp → Seat (Grammarly); Autonomy cao + Attribution cao → Outcome (Intercom Fin) |

## Cách định giá (Pricing models)

| Thuật ngữ | Nghĩa | Ví dụ |
|---|---|---|
| **Seat / Flat pricing** | $X cố định / người dùng / tháng. Dễ dự đoán. Phù hợp khi Autonomy thấp + Attribution thấp. | Grammarly $12/người dùng, Slack AI $7/người dùng, ChatGPT Team $25/người dùng |
| **Usage-based pricing** | $X / đơn vị dùng (theo token, theo lệnh gọi, theo yêu cầu). Biến động theo lượng dùng. Phù hợp khi Autonomy cao + Attribution thấp. | OpenAI API $3/1M token đầu vào, AWS trả theo từng lệnh gọi, Pinecone trả theo từng truy vấn |
| **Outcome-based pricing** | $X / kết quả thực tế (mỗi ticket được giải quyết, mỗi tranh chấp thắng). Phù hợp khi Autonomy cao + Attribution cao. | Intercom Fin $0.99/vấn đề giải quyết, Chargeflow tính theo từng tranh chấp chargeback thắng, Zendesk $1.50/vấn đề giải quyết |
| **CAMP test** | 4 chuẩn để Outcome-based bán được: **C**ountable (đếm được), **A**ligned (cùng hướng với khách + nhà cung cấp), **M**eaningful (có ý nghĩa với người mua), **P**redictable (dự báo được khối lượng). Hỏng 1 trong 4 → không bán được. | "1 vấn đề giải quyết" qua CAMP; "1 cuộc hội thoại" hỏng Meaningful (người mua không quan tâm số lượt chat) |
| **Hybrid pricing** | Pha trộn Seat nền + Usage credits, hoặc nhiều tầng Outcome. Phù hợp khi Autonomy + Attribution ở mức vừa. | Cursor $20/người dùng + credit AI; Canva $15/người dùng + 500 credit; Clay $149/$349/$800 theo tầng |
| **Pay-for-output** | Định giá dựa trên kết quả AI tạo ra. Là một dạng Outcome-based. | Intercom Fin $0.99/vấn đề giải quyết (chỉ trả tiền khi ticket được giải quyết) |
| **Value metric** | Đơn vị mà khách hàng trả tiền cho. Phải đếm được + có ý nghĩa với người mua + gắn với giá trị AI tạo ra. | "1 ticket giải quyết" (Intercom), "1 ghế luật sư" (Harvey), "1 ảnh sinh ra" (DALL-E) |
| **Usage Anxiety** | Người dùng tự hạn chế xài AI vì sợ hóa đơn tăng → AI không được dùng thật → giá trị bị nén lại. Đây là rủi ro chính của Usage-based và Hybrid. | Cảnh báo credit của Cursor làm người dùng ngại dùng → giá trị AI giảm |

## Các khoản chi phí (Cost components)

| Thuật ngữ | Nghĩa | Ví dụ |
|---|---|---|
| **Cost per task** | Chi phí một lần AI chạy = (token vào × giá vào + token ra × giá ra) / 1M. | Claude 3.5 Sonnet: 800 token vào × $3 + 400 token ra × $15 / 1M = $0.0084 |
| **API cost** | Chi phí gọi mô hình AI qua API (tính theo token / theo lệnh gọi). Thường chiếm 1-30% tổng chi phí trong giai đoạn pilot. | OpenAI GPT-4o $2.50/1M token vào, Anthropic Claude 3.5 $3/1M token vào |
| **Tooling cost** | Chi phí hạ tầng ngoài mô hình AI: vector DB, monitoring, orchestration. Thường cố định theo tháng. | Pinecone $70/tháng, Langfuse $50/tháng, Helicone $50/tháng |
| **Human review cost** | Thời gian × lương theo giờ của người kiểm tra lại đầu ra AI. Thường chiếm phần lớn chi phí khi đề bài yêu cầu 100% người duyệt. | 3 phút kiểm tra × $25/giờ / 60 = $1.25/lần × 1,000 lần = $1,250/tháng |
| **Setup cost** | Chi phí một lần: tích hợp, rà soát bảo mật, viết câu lệnh AI, đào tạo. Phải chia đều theo độ dài pilot. | 1 kỹ sư × 2 tuần × $2,000 = $4,000 / 3 tháng pilot = $1,333/tháng |
| **Loaded hourly rate** | Lương theo giờ đã cộng đầy đủ chi phí ẩn = lương cơ bản × 1.3-1.5 (phúc lợi + thuế + chi phí gián tiếp + văn phòng). Dùng chung cho cả chi phí (người kiểm tra) và giá trị (thời gian tiết kiệm). | $20/giờ lương cơ bản × 1.25 = $25/giờ đã cộng đầy đủ |
| **Monthly volume** | Số lần AI chạy mỗi tháng = Khối lượng mỗi ngày của nhóm thử nghiệm × 22 ngày làm việc. | 160 việc/ngày × 22 = 3,520 việc/tháng |

## Các thành phần giá trị (Value components)

| Thuật ngữ | Nghĩa | Ví dụ |
|---|---|---|
| **Gross time saved** | Thời gian tiết kiệm thô, chưa trừ các phụ phí ẩn. | AI giúp tiết kiệm 5 phút tra tài liệu + 4 phút viết nháp = 9 phút thô |
| **NET time saved** | Thời gian tiết kiệm thực tế = Thô − thời gian chờ AI − người kiểm tra − chuyển ngữ cảnh − sửa lại. Thường còn 40-60% so với thô. | 9 phút thô − 0.3 chờ − 3 kiểm tra − 0.5 chuyển ngữ cảnh − 0.6 sửa lại = 4.6 phút thực tế |
| **Adoption rate** | Tỷ lệ % người dùng pilot thật sự dùng AI. Mức thực tế: 50-80% nếu bắt buộc, 20-50% nếu tự nguyện. | 5 nhân viên pilot × 65% sử dụng thực tế = 3.25 nhân viên dùng = 65% tiềm năng giá trị |
| **Quality factor** | Tỷ lệ % đầu ra AI dùng được mà không cần sửa lớn. Theo loại việc: 80-95% cho phân loại, 60-80% cho viết nháp, 70-85% cho tóm tắt, 50-70% cho việc sáng tạo, 40-65% cho việc phức tạp. | Viết nháp với Claude 3.5: thường đạt 75-85% |
| **Rework cost** | Thời gian sửa lại các đầu ra AI tệ khi chất lượng không đạt. Tăng khi chất lượng giảm. | 20% bản nháp phải viết lại × 3 phút mỗi lần viết lại = trung bình 0.6 phút sửa lại / việc |

## ROI + Quyết định

| Thuật ngữ | Nghĩa | Ví dụ |
|---|---|---|
| **ROI ratio** | Tỷ lệ giá trị / chi phí = Giá trị mỗi tháng / Chi phí mỗi tháng. Viết dạng số:1 (vd: 2.07:1). | $5,797 giá trị / $2,803 chi phí = 2.07:1 |
| **Break-even** | Ngưỡng tỷ lệ sử dụng thực tế hoặc chất lượng tại đó ROI = 1:1. Pilot không trụ nổi nếu rơi dưới ngưỡng này. | Điểm hòa vốn theo tỷ lệ sử dụng: chi phí / (giá trị thô × tỷ lệ đạt chất lượng) = 31% |
| **Sensitivity analysis** | Bảng cho thấy ROI thay đổi thế nào khi 1-2 biến (tỷ lệ sử dụng, chất lượng, chi phí) thay đổi. Cho thấy "vùng đẹp" và "ngưỡng sống chết". | Ma trận ROI theo tỷ lệ sử dụng × chất lượng: 4×4 ô, xác định các ô có ROI > 3:1 |

## Kịch bản xấu (Stress Test)

| Thuật ngữ | Nghĩa | Ví dụ |
|---|---|---|
| **Stress test** | Mô phỏng các kịch bản xấu để xem kinh tế có sống nổi không. Khác phân tích nhạy cảm (thay đổi nhỏ) — kịch bản xấu thay đổi lớn (2-3 lần hoặc 30-50%). | 5 kịch bản: cơ bản, dùng nặng, sử dụng thực tế thấp, chất lượng giảm, nhà cung cấp đổi giá |
| **Heavy usage** | Kịch bản khối lượng tăng nhiều (mẫu hành vi của power user — 20% người dùng chiếm 80% dung lượng). | Khối lượng × 2-3, kiểm tra xem chi phí có bị thổi phồng nhanh hơn giá trị không |
| **Power user pattern** | Một nhóm nhỏ người dùng (10-20%) xài AI cực kỳ nhiều (có thể gấp 5-100 lần mức trung bình), kéo lệch chi phí lên trong khi giá trị không tăng tương ứng. Đây là nguyên nhân chính khiến kịch bản dùng nặng phá vỡ kinh tế. | Pilot Replit 2024: 20% người dùng chiếm 80% dung lượng → biên lợi nhuận âm; Cursor phải đặt trần credit |
| **Cost Variance Problem** | Chi phí biến động lớn giữa các người dùng (do power user kéo lệch), khiến PM khó dự báo ngân sách tháng tới — phương sai chi phí cao hơn nhiều so với SaaS truyền thống. | Pilot 5 người, chi phí trung bình $300/người nhưng dao động $50-$1,500/người → CFO ngại duyệt mở rộng quy mô |
| **Low adoption** | Kịch bản chỉ 30-40% người dùng pilot thực sự dùng. | Tỷ lệ sử dụng 65% → còn 30%, giá trị sụp, chi phí vẫn cố định |
| **Quality failure** | Kịch bản chất lượng AI giảm mạnh (50-60% thay vì 80%). | Kho tài liệu lỗi thời, gặp trường hợp khó nhằn, mô hình thiếu kiến thức ngành — chất lượng còn 50% |
| **Provider shock** | Kịch bản nhà cung cấp đổi giá hoặc ngừng phát hành mô hình. | Anthropic ngừng phát hành Claude 3.5 → Claude 4 đắt gấp 3 |
| **Combined worst case** | 2 kịch bản xấu nhất xảy ra đồng thời. Bài kiểm tra khả năng chịu đựng cao nhất. | Tỷ lệ sử dụng thấp (30%) + chất lượng giảm (50%) → ROI 0.6:1 |
| **"Survives X/5"** | Đếm số kịch bản (trên tổng 5) mà ROI vẫn ≥ 1.5:1 (ngưỡng tối thiểu). Tiêu chí cho quyết định cuối: GO cần sống 4-5/5, CONDITIONAL 2-3/5, NO-GO dưới 2/5. | Cơ bản 2.07 + dùng nặng 2.17 + nhà cung cấp đổi giá 1.95 đều ≥ 1.5 → sống 3/5 → CONDITIONAL |

## Quyết định cuối (Verdict)

| Thuật ngữ | Nghĩa | Ví dụ |
|---|---|---|
| **Verdict** | Quyết định cuối về pilot AI: GO / CONDITIONAL / NO-GO. Phải bảo vệ được bằng số. | "CONDITIONAL GO kèm 3 điều kiện" |
| **GO** | Tiến hành pilot không kèm điều kiện. ROI cơ bản > 3:1, sống 4-5/5 kịch bản, kết hợp xấu nhất > 1.5:1. | Hiếm cho pilot AI quy mô nhỏ (thường ROI > 5:1 mới chắc GO) |
| **CONDITIONAL** | Tiến hành kèm điều kiện rõ + giám sát + ngưỡng dừng. ROI cơ bản 1.5-3:1, hoặc sống 2-3/5 kịch bản, hoặc kết hợp xấu nhất 1-1.5:1. Là kết quả phổ biến nhất (70%+ pilot AI). | "CONDITIONAL: tỷ lệ sử dụng ≥ 60% tháng 1, ký hợp đồng tối đa 6 tháng" |
| **NO-GO** | Không khả thi ở quy mô hiện tại. ROI cơ bản < 1.5:1, hoặc sống dưới 2/5 kịch bản. Phải liệt kê 2-3 thay đổi để có thể khả thi (không từ chối khô khốc). | "NO-GO ở quy mô hiện tại. Cần: mô hình rẻ hơn + mở rộng nhóm pilot + thương lượng lại ràng buộc" |
| **Monitoring metrics** | 3-5 chỉ số theo dõi hàng tuần/tháng để biết pilot có đi đúng hướng không. | Tỷ lệ sử dụng, chi phí mỗi việc, chất lượng, CSAT, tốc độ đốt ngân sách |
| **Stop / Pivot trigger** | Ngưỡng cứng: nếu X xảy ra trong khoảng Y → tạm dừng / đổi hướng. | "Tỷ lệ sử dụng < 40% trong 30 ngày liên tiếp → tạm dừng để rà soát" |

## Vai trò và người mua

| Thuật ngữ | Nghĩa | Ví dụ |
|---|---|---|
| **Buyer** | Người ra quyết định mua sản phẩm AI. Khác với người dùng. | Đề bài #1: CTO; Đề bài #4: Managing Partner; Đề bài #7: Giám đốc chuỗi cung ứng |
| **Buying trigger** | Lý do người mua quyết định mua NGAY HÔM NAY (không phải năm sau). | Điểm đau (tỷ lệ khách rời 18%) + chi phí phương án thay thế cao (tuyển thêm 5 nhân viên hỗ trợ tốn $300K/năm) |
| **Delegator vs Prosumer** | Delegator = người giao trọn việc cho AI (autonomy cao). Prosumer = người tham gia làm cùng AI (autonomy thấp). | Delegator: Intercom Fin tự trả lời ticket. Prosumer: GitHub Copilot gợi ý, lập trình viên tự chọn. |

## Kinh tế đặc thù của sản phẩm AI

| Thuật ngữ | Nghĩa | Ví dụ |
|---|---|---|
| **Variable cost** | Chi phí thay đổi theo lượng dùng (đối lập với chi phí cố định). Sản phẩm AI có phần lớn chi phí thuộc loại biến đổi. | Chi phí API = mỗi lệnh gọi. Mỗi người dùng × mỗi việc = chi phí cộng dồn |
| **Marginal cost** | Chi phí phát sinh thêm khi có thêm 1 người dùng hoặc 1 việc. SaaS truyền thống gần như bằng 0; với AI = chi phí API + công cụ phụ trợ. | Thêm 1 ticket = $0.0084 chi phí API + $0.50 chi phí người kiểm tra = $0.51 chi phí biên |
| **Rented land** | Phụ thuộc nền tảng / nhà cung cấp bên ngoài (OpenAI, Anthropic, Google). Rủi ro lớn nếu nhà cung cấp đổi giá hoặc ngừng phát hành. | Replit dùng Anthropic + OpenAI — rủi ro nhà cung cấp hiện hữu thật |
| **Data flywheel** | AI tự cải thiện nhờ dữ liệu sử dụng (vòng phản hồi). Giá trị tăng dần theo thời gian. | Cursor học từ việc người dùng chấp nhận/từ chối gợi ý → chất lượng tăng dần |
| **Worked example** | Ví dụ tính từ đầu đến cuối, có số cụ thể (không chung chung). | Slide 7 bài giảng: Support Copilot từ đơn vị AI làm việc → chi phí → giá trị → ROI |

## Lỗi hay mắc

| Lỗi | Cách đúng |
|---|---|
| Nói "AI tự làm xong" mà đề bài yêu cầu 100% người duyệt | Autonomy thấp đúng thực tế |
| Đặt chất lượng 95% | Theo mốc thực tế: 60-85% là hợp lý |
| Đặt tỷ lệ sử dụng thực tế 90% | Thực tế 50-80% nếu pilot bắt buộc |
| Dùng thời gian tiết kiệm thô (Gross) | Tính thực tế = Thô − chờ − kiểm tra − chuyển ngữ cảnh − sửa lại |
| Chi phí mỗi việc = $0.001 (chỉ tính API) | Phải cộng cả người kiểm tra + công cụ phụ trợ + chi phí dựng đầu |
| Quyết định GO chắc nịch | CONDITIONAL là mặc định cho pilot AI |
| Điều kiện chung chung "theo dõi tỷ lệ sử dụng" | Cụ thể: "Tỷ lệ sử dụng ≥ 60% tháng 1, kiểm tra hàng tuần" |
| Kịch bản kết hợp xấu = 1 kịch bản | Kết hợp = 2 kịch bản xảy ra đồng thời |

---

## Cách dùng Glossary trong worksheet

- Khi viết worksheet và gặp thuật ngữ → tra glossary để dùng cho đúng.
- Khi hỏi AI → có thể dán một phần glossary vào đầu cuộc trò chuyện để AI hiểu cách AI20k dùng từ.
- Khi trình bày → tra glossary để chắc khán giả hiểu thuật ngữ.

Nếu gặp thuật ngữ chưa có trong glossary → ghi vào sổ tay nhóm, đóng góp cho khóa sau.
