# 00 · User Journey Simulation — Đóng vai Tourist

> **Mục tiêu**: Trước khi tính chi phí, nhóm phải hình dung được khách hàng thật sự hỏi gì, hỏi như thế nào, và 1 conversation thực tế trông ra sao.
>
> **Thời gian**: 8 phút (trong 15 phút phần Setup)

---

## Tại sao phải làm bước này?

Nếu nhóm bắt đầu tính cost mà chưa biết tourist hỏi gì → mọi con số chỉ là lý thuyết. Bước này buộc nhóm "chạm" sản phẩm trước khi mở Excel.

---

## Bước 1 — Mỗi người đóng vai 1 tourist (4 phút)

Tưởng tượng mình là 1 khách du lịch nước ngoài đang plan trip Việt Nam. Bạn vừa mở website công ty du lịch, thấy có chatbot ở góc màn hình. Bạn sẽ hỏi gì?

Trước khi viết, tự hỏi:

- Mình từ đâu đến? Mỹ, Anh, Hàn, Nhật, Úc?
- Đi 1 mình hay đi nhóm? Budget khoảng bao nhiêu?
- Đã biết gì về Việt Nam? Lần đầu đến hay đã đến rồi?
- Mình lo lắng điều gì nhất? (visa, an toàn, ngôn ngữ, thời tiết, ẩm thực, lừa đảo...)

Viết **5–7 câu hỏi bằng tiếng Anh** mình sẽ thật sự gửi cho chatbot. Viết câu hỏi tự nhiên, đúng giọng tourist — không phải đặt câu hỏi "nghe có vẻ technical".

→ Mỗi người viết vào ô dưới (chưa có gì sẵn — đừng nhìn người bên cạnh):

### Tourist #1 — James (Tên thành viên: Thành)
Hồ sơ: Người Anh, 30 tuổi, đi solo, lần đầu đến Việt Nam, budget £2,000/12 ngày, lo nhất về giao thông và thực phẩm an toàn.

```text
1. "Do UK citizens need a visa to visit Vietnam? I'm planning a 12-day trip."
2. "What's the safest way to travel between Hanoi and Ho Chi Minh City — train or plane?"
3. "I want to try authentic Vietnamese food but I'm worried about food hygiene. Any advice?"
4. "What are the top 5 things a first-time visitor to Vietnam must do or see?"
5. "Is it safe to use grab bikes in Hanoi city center as a tourist?"
6. "How much cash should I bring? Is card payment widely accepted in tourist areas?"
7. "What's the best sim card option for tourists in Vietnam — any recommendations?"
```

### Tourist #2 — Min-jun (Tên thành viên: Thành)
Hồ sơ: Người Hàn Quốc, 27 tuổi, đi cùng người yêu, quan tâm ẩm thực và văn hóa địa phương, muốn đi Đà Nẵng và Hội An.

```text
1. "We're a Korean couple visiting Da Nang and Hoi An for 6 days. Can you suggest a detailed itinerary?"
2. "Is March a good time to visit Da Nang? What's the weather usually like?"
3. "What local foods in Hoi An are a must-try — especially for someone who loves spicy food?"
4. "How do we get from Da Nang airport to Hoi An? Is it easy to find transport?"
5. "Are there any good cooking classes in Hoi An that teach traditional Vietnamese recipes?"
6. "Do we need to book Hoi An Ancient Town tickets in advance, or can we just walk in?"
```

### Tourist #3 — Emma (Tên thành viên: Thành)
Hồ sơ: Người Đức, 38 tuổi, đi cùng chồng và con gái 7 tuổi, lo về sức khoẻ và hoạt động phù hợp cho trẻ.

```text
1. "We're traveling with our 7-year-old daughter. Which parts of Vietnam are most child-friendly?"
2. "What vaccinations are recommended before visiting Vietnam from Germany?"
3. "Are there any water parks or family-friendly theme parks near Hanoi or Da Nang?"
4. "My daughter has a nut allergy — how easy is it to manage food allergies in Vietnamese restaurants?"
5. "What is the hospital situation like in Da Nang if our child gets sick?"
6. "Is Halong Bay cruise suitable for a 7-year-old? What activities can she join?"
7. "How do German citizens apply for a Vietnam e-visa? How long does it take?"
```

---

## Bước 2 — Gom lại và phân loại (4 phút)

Cả nhóm chụm vào, gom tất cả câu hỏi lại. Trước khi điền bảng, thảo luận 1 phút:

- Có câu hỏi nào lặp lại giữa các tourist không?
- Có chủ đề nào không ai trong nhóm nghĩ tới ban đầu nhưng quan trọng?
- Câu nào chatbot có thể trả lời được? Câu nào cần chuyển sang nhân viên thật?

5 intent có sẵn (tham khảo `cost-reference-card.md` mục 2):

- **Visa/Policy** — chính sách, thủ tục nhập cảnh
- **Điểm đến/Guide** — gợi ý đi đâu, làm gì, ăn gì
- **Thời tiết/Sự kiện** — info real-time
- **Tour/Booking** — đặt vé, đặt tour, đặt phòng → chuyển sales
- **Khiếu nại** — phàn nàn → chuyển manager

Sau khi gom, điền bảng phân loại:

| # | Câu hỏi (1 dòng) | Intent thuộc loại nào | Cần bao nhiêu lượt chat để xong? | Bot trả lời hay chuyển người? |
|---|---|---|---|---|
| 1 | Do UK citizens need a visa to Vietnam? | Visa/Policy | 3–4 lượt (loại visa, thời hạn, phí) | ✅ Bot |
| 2 | Safest way to travel Hanoi → HCMC? | Điểm đến/Guide | 3 lượt (tàu/máy bay, giá, thời gian) | ✅ Bot |
| 3 | Is street food safe? Any advice? | Điểm đến/Guide | 2–3 lượt | ✅ Bot |
| 4 | Top 5 things for first-time visitor | Điểm đến/Guide | 4–5 lượt (gợi ý + lý do) | ✅ Bot |
| 5 | Is it safe to use Grab bikes in Hanoi? | Điểm đến/Guide | 2 lượt | ✅ Bot |
| 6 | 6-day itinerary Da Nang + Hoi An | Điểm đến/Guide | 5–6 lượt (chi tiết từng ngày) | ✅ Bot |
| 7 | Weather in Da Nang in March? | Thời tiết/Sự kiện | 2–3 lượt | ✅ Bot (cần real-time) |
| 8 | Local food recommendations in Hoi An | Điểm đến/Guide | 3 lượt | ✅ Bot |
| 9 | Book Halong Bay cruise for family | Tour/Booking | 1 lượt rồi handoff | 🔁 Chuyển sales |
| 10 | Vaccinations required from Germany? | Visa/Policy | 3 lượt | ✅ Bot |
| 11 | Child-friendly cities in Vietnam? | Điểm đến/Guide | 4 lượt | ✅ Bot |
| 12 | Managing food allergy in Vietnam | Điểm đến/Guide | 3 lượt | ✅ Bot |
| 13 | Hospital situation in Da Nang | Điểm đến/Guide | 2 lượt | ✅ Bot |
| 14 | German e-visa application process | Visa/Policy | 3–4 lượt | ✅ Bot |
| 15 | Book cooking class in Hoi An | Tour/Booking | 1 lượt rồi handoff | 🔁 Chuyển sales |

---

## Bước 3 — Rút insight cho nhóm (cuối phần Setup)

Trả lời nhanh 4 câu — sẽ dùng lại ở các bước sau:

**Tổng số câu hỏi nhóm gom được**:

```text
19 câu hỏi (3 tourist × 6–7 câu mỗi người)
```

**Phân bố intent thực tế của nhóm** (% mỗi intent):

```text
Guide:     60%  (9/15 câu — itinerary, food, transport, safety)
Visa:      20%  (3/15 câu — UK visa, German e-visa, vaccinations)
Weather:    7%  (1/15 câu — Da Nang March)
Booking:   13%  (2/15 câu — cruise booking, cooking class)
Khiếu nại:  0%  (không ai đóng vai nghĩ đến khiếu nại)
```

**Số lượt chat trung bình để xong 1 chủ đề**:

```text
Guide: ~3.5 lượt (câu hỏi itinerary / food phức tạp hơn câu hỏi transport)
Visa: ~3 lượt (hỏi điều kiện, thủ tục, thời gian xét duyệt)
Weather: ~2 lượt (confirm mùa + nhiệt độ + gợi ý trang phục)
Booking: 1 lượt rồi chuyển người — khách nói "I'd like to book" là handoff ngay
```

**Đối chiếu với đề bài** (Scenario A = 4 lượt, Scenario B = 7 lượt):

```text
Hợp lý vì Guide chiếm 60%, trung bình 3.5 lượt → gần với Scenario A (4 lượt).
Scenario B (7 lượt) xảy ra khi tourist mix nhiều intent: hỏi visa → hỏi điểm đến
→ hỏi thời tiết → rồi hỏi thêm chi tiết. Ví dụ Emma hỏi vaccination rồi hỏi tiếp
về bệnh viện và hoạt động cho trẻ → 1 conversation có thể đến 6–7 lượt.
```

**Insight bất ngờ — điều gì nhóm chỉ hiểu sau khi đóng vai?**

```text
1. Tourist lo về sức khỏe và an toàn nhiều hơn tưởng: food hygiene, allergy,
   hospital — nhóm ban đầu không nghĩ đến nhưng đây là concern thực tế quan trọng.
2. Câu hỏi booking (cruise, cooking class) cực ngắn — khách hỏi 1 câu là
   chuyển ngay sang sales, không phải conversation dài. % booking cao không
   đồng nghĩa với LLM cost cao.
3. Tourist Hàn và Anh hỏi theo kiểu khác nhau: Min-jun hỏi rất cụ thể (Da Nang
   March, Hoi An Ancient Town), James hỏi tổng quát hơn (top 5, safest way) —
   chatbot cần handle cả 2 phong cách.
```

---

## Bảng kiểm trước khi sang file tiếp theo

- [x] Mỗi người trong nhóm đã viết ≥5 câu hỏi tourist
- [x] Đã gom + phân loại intent cho ≥10 câu (bảng trên — 15 câu)
- [x] Đã có phân bố intent % của nhóm (so với đề bài)
- [x] Có ít nhất 1 insight về cách tourist thật sự dùng chatbot

Xong → mở `01-base-flow.md`.
