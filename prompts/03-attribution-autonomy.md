# Câu lệnh AI 3 — Đặt sản phẩm vào ma trận Attribution × Autonomy

**Dùng khi**: đầu Bước 2 Lab — nhóm đã có Cost Model, cần đặt sản phẩm AI vào ma trận 2×2 *(2 trục: AI có làm tự chủ không × AI có chịu trách nhiệm rõ cho kết quả không)* để chọn cách định giá phù hợp.

**Công cụ gợi ý**: Claude, ChatGPT, Gemini.

**Lưu kết quả vào**: `worksheet/02-pricing-value/1-attribution-autonomy.md`.

**Thời gian**: 10–15 phút.

---

## Trước khi vào câu lệnh — 5 câu nhóm tự trả lời

AI hay đặt sai vị trí, đặc biệt là cho AI "điểm cao về tự chủ" trong khi đề bài có ràng buộc bắt người kiểm tra. Trả lời 5 câu này trước để nhóm có khung tự kiểm tra.

1. Usage Unit đã chốt là gì? (Cả hai trục đều đánh giá theo đơn vị này.)
2. Đọc lại trường ràng buộc (trường 5 của đề bài): AI tự làm xong việc, hay chỉ hỗ trợ người làm việc?
3. Đầu ra AI có hiển thị trực tiếp cho khách hàng cuối không (vd: khách thấy AI trả lời), hay chỉ nội bộ đội thấy?
4. Có thể nói thẳng "AI đã làm việc X" không (cụ thể), hay chỉ "AI giúp đội làm việc X"?
5. Nếu đề bài có "100% người kiểm tra" → trục tự chủ tự động xuống thấp.

---

## Câu lệnh chính (dán sau `00-context.md` và kết quả Cost Model)

```text
Bạn là chuyên gia chiến lược sản phẩm AI, chuyên về mô hình định giá.
Dựa trên bối cảnh ở trên (đề bài + Usage Unit + Cost Model), giúp nhóm
tôi:

1. Đặt sản phẩm AI vào ma trận Attribution × Autonomy.
2. Đề xuất cách định giá phù hợp tự nhiên.
3. Đối chiếu với sản phẩm thật.

Bối cảnh ma trận:
- Autonomy (tự chủ): AI tự làm xong việc (cao) — vs — AI hỗ trợ người
  (thấp).
- Attribution (gắn rõ với AI): rõ là AI tạo ra kết quả (cao) — vs —
  khó tách AI khỏi công sức của đội (thấp).

Mỗi ô của ma trận gợi ý một mô hình giá tự nhiên:
- Tự chủ thấp + Gắn thấp  → tính theo người dùng (vd: Grammarly, Slack AI)
- Tự chủ thấp + Gắn cao   → kết hợp (vd: Cursor, Canva — người dùng + tín dụng)
- Tự chủ cao + Gắn thấp   → tính theo lượng dùng (vd: API OpenAI, AWS)
- Tự chủ cao + Gắn cao    → tính theo kết quả (vd: Intercom Fin, Chargeflow)

Yêu cầu:

Phần 1 — Đánh giá trục tự chủ:
- Đề bài rơi vào: Thấp ___ (AI hỗ trợ, người ra quyết định cuối)
                  Cao ___ (AI tự ra quyết định / hành động)
- 2–3 câu lý do dựa trên: ràng buộc (trường 5), ranh giới rủi ro
  (trường 9), quy trình (trường 2).

Cảnh báo: nếu đề bài có "100% người kiểm tra" hoặc "người duyệt trước
khi gửi" → KHÔNG đánh giá tự chủ cao được.

Phần 2 — Đánh giá trục gắn-rõ-với-AI:
- Thấp: khó tách phần AI khỏi đội (vd: AI giúp đội viết → kết quả là
  "đội viết tốt", không nói rõ AI làm phần nào).
- Cao: rõ AI tạo ra kết quả (vd: AI gắn cờ 1 điều khoản → rõ AI tạo
  cảnh báo đó).
- 2–3 câu lý do.

Phần 3 — Vị trí trên ma trận:
- Tự chủ: ___
- Gắn rõ với AI: ___
- Ô: ___
- Định giá tự nhiên cho ô này: ___

Phần 4 — Đối chiếu sản phẩm thật:
Tìm 2 sản phẩm AI đang chạy thật trong cùng ô (cùng ngành hoặc khác
ngành nhưng cùng mô hình):
- Sản phẩm A: tên + cách định giá + URL trang giá
- Sản phẩm B: tên + cách định giá + URL trang giá

Có quy luật chung không? Cách định giá họ chọn gợi ý gì cho nhóm tôi?

Phần 5 — Trường hợp đứng giữa:
Đề bài có rơi vào "vừa thấp vừa cao" không? Nếu có:
- Nghiêng về trục nào trước (tự chủ hay gắn-rõ)?
- Lý do (ràng buộc nào, quy luật nào)?

Khi đứng giữa, kết hợp (Hybrid: tính theo người + tính theo lượng) thường
là lựa chọn mặc định an toàn.

Yêu cầu trình bày:
- Viết tiếng Việt thoát nghĩa.
- Mỗi đánh giá có lý do cụ thể, không chỉ "tôi nghĩ".

Yêu cầu phản biện:
- Nếu nhóm tôi đánh giá tự chủ cao nhưng đề bài có người kiểm tra → cảnh
  báo mâu thuẫn.
- Nếu nhóm tôi đánh giá gắn-rõ cao nhưng người mua khó đo → cảnh báo rủi
  ro khi đi bán.
- Nếu cách định giá đề xuất không khớp với người mua (giám đốc kỹ thuật
  vs giám đốc tài chính) → cảnh báo trở ngại.
```

---

## Iterate — đẩy AI sâu hơn khi bản nháp chưa đủ

### Khi nhóm muốn đối chiếu vị trí với sản phẩm thật

```text
Vị trí AI gán cho đề bài của tôi là [Tự chủ ___ + Gắn-rõ ___].

Đối chiếu với 3 sản phẩm:

1. (sản phẩm cùng ngành — vd: Zendesk AI cho support)
   - Vị trí của họ trên ma trận: ___
   - Cách định giá: ___
   - Có khớp với ô tôi đề xuất không?

2. (sản phẩm khác ngành nhưng cùng mô hình hoạt động — vd: Harvey AI
   cho luật)
   - (như trên)

3. (sản phẩm có ràng buộc tương tự — vd: đề bài có người kiểm tra → tìm
   sản phẩm cũng có người kiểm tra)
   - (như trên)

Nếu cả 3 đều ở cùng ô và đều dùng định giá theo người dùng → xác nhận
cho đề bài của tôi.
Nếu 3 sản phẩm rải khắp 4 ô → đánh giá lại lý do của nhóm.
```

### Khi nhóm muốn chất vấn đánh giá trục tự chủ

```text
Tôi đánh giá tự chủ = CAO, nhưng đề bài có ràng buộc "người duyệt trước
khi gửi".

Có mâu thuẫn không?
- Nếu người luôn duyệt → AI không thực sự tự chủ → phải đánh giá THẤP.
- Nếu người chỉ duyệt 50% trường hợp → ở giữa, đánh giá lại.
- Nếu người chỉ duyệt tầng cơ bản, các tầng khác AI tự làm → tách: tầng
  cơ bản = tự chủ thấp, tầng còn lại = tự chủ cao?

Đề xuất: đa số đề bài có ràng buộc duyệt → đánh giá TỰ CHỦ THẤP. Không
được đánh giá cao chỉ vì "AI làm phần lớn việc" — người duyệt = quyết
định cuối.
```

### Khi 2 cách định giá đều hợp lý, phải chọn 1

```text
Ô của tôi = ___ → định giá tự nhiên = ___.

Có 2 lựa chọn khác cũng hợp lý:
- Lựa chọn A: ___, lý do hợp lý
- Lựa chọn B: ___, lý do hợp lý

So sánh 3 lựa chọn qua 4 góc nhìn:

| Góc nhìn | Định giá tự nhiên | Lựa chọn A | Lựa chọn B |
|---|---|---|---|
| Người mua dễ duyệt? | | | |
| Chi phí dự đoán được? | | | |
| Bảo vệ được ROI? | | | |
| Có gây "lo lắng khi dùng" cho người dùng cuối? | | | |

Đề xuất cuối: ___ vì ___.
```

---

## Trước khi dán kết quả vào worksheet — nhóm tự rà soát

- Trục tự chủ có khớp với ràng buộc trong đề bài không?
- Trục gắn-rõ có bảo vệ được không (người mua đo được phần AI tạo ra)?
- Vị trí có rõ ràng, không "ở giữa cả 4 ô"?
- Sản phẩm đối chiếu thật có cùng ô không?
- Cách định giá đề xuất có khớp với người mua và cấu trúc chi phí không?

---

## Câu hỏi mở rộng (chỉ làm khi còn thời gian)

```text
Sau khi định vị, suy nghĩ 3 góc chiến lược:

1. Chuyển đổi cách định giá theo thời gian:
   - Phiên bản đầu (MVP): tính theo người dùng, tự chủ thấp + gắn-rõ thấp.
   - 2 năm sau: AI quen, mở cho phép tự gửi → tự chủ cao hơn → chuyển
     sang tính theo kết quả?
   - Khoảng đệm chuyển đổi bao lâu?

2. Cùng cách định giá có hợp với người mua khác không?
   - Giám đốc kỹ thuật: quan tâm chi phí có dự đoán được không.
   - Giám đốc tài chính: quan tâm ROI có bảo vệ được không.
   - Phó tổng vận hành: quan tâm tỷ lệ sử dụng thực tế.

3. Bán riêng hay bán kèm sản phẩm cũ?
   - Bán kèm: dễ bán hơn nhưng khó đo riêng giá trị AI.
   - Bán riêng: bảo vệ được giá trị AI rõ ràng nhưng tăng cản trở khi
     đi qua quy trình mua.

3 câu này chuẩn bị cho buổi trình bày + hỏi đáp với giảng viên.
```
