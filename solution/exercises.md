# Ngày 1 — Bài Tập & Phản Ánh
## Nền Tảng LLM API | Phiếu Thực Hành

**Thời lượng:** 1:30 giờ  
**Cấu trúc:** Lập trình cốt lõi (60 phút) → Bài tập mở rộng (30 phút)

---

## Phần 1 — Lập Trình Cốt Lõi (0:00–1:00)

Chạy các ví dụ trong Google Colab tại: https://colab.research.google.com/drive/172zCiXpLr1FEXMRCAbmZoqTrKiSkUERm?usp=sharing

Triển khai tất cả TODO trong `template.py`. Chạy `pytest tests/` để kiểm tra tiến độ.

**Điểm kiểm tra:** Sau khi hoàn thành 4 nhiệm vụ, chạy:
```bash
python template.py
```
Bạn sẽ thấy output so sánh phản hồi của GPT-4o và GPT-4o-mini.
=== Comparing models ===
gpt4o_response: Temperature controls the randomness of the model's output by adjusting the probability distribution of the next word, while top_p (nucleus sampling) limits the selection to a subset of the vocabulary that cumulatively represents a specified probability mass, ensuring more coherent and contextually appropriate responses.
mini_response: Temperature controls the randomness of the output by scaling the probabilities of the predicted words, while top_p (nucleus sampling) limits the selection to the smallest possible set of words whose cumulative probability exceeds a specified threshold, promoting diversity in generated text.
gpt4o_latency: 2.0383386611938477
mini_latency: 1.8282639980316162
gpt4o_cost_estimate: 5.8666666666666665e-05
---

## Phần 2 — Bài Tập Mở Rộng (1:00–1:30)

### Bài tập 2.1 — Độ Nhạy Của Temperature
Gọi `call_openai` với các giá trị temperature 0.0, 0.5, 1.0 và 1.5 sử dụng prompt **"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**
0.0:
gpt4o_response: Một sự thật thú vị về Việt Nam là đất nước này có một hệ thống hang động lớn nhất thế giới, đó là hang Sơn Đoòng. Hang Sơn Đoòng nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng, tỉnh Quảng Bình. Hang được phát hiện vào năm 1991 bởi một người dân địa phương tên là Hồ Khanh, nhưng mãi đến năm 2009, một đoàn thám hiểm người Anh mới chính thức khảo sát và công bố rộng rãi. Hang Sơn Đoòng có kích thước khổng lồ với chiều dài hơn 5 km, cao 200 m và rộng 150 m, đủ lớn để chứa cả một tòa nhà chọc trời 40 tầng. Bên trong hang có hệ sinh thái riêng biệt, với rừng cây, sông ngầm và các loài động thực vật độc đáo.
mini_response: Một sự thật thú vị về Việt Nam là đất nước này có hơn 3.000 km bờ biển, với nhiều bãi biển đẹp nổi tiếng như Mỹ Khê, Nha Trang và Phú Quốc. Việt Nam cũng có nhiều vịnh đẹp, trong đó nổi bật nhất là Vịnh Hạ Long, được UNESCO công nhận là Di sản Thiên nhiên Thế giới với hàng nghìn hòn đảo đá vôi kỳ thú. Điều này không chỉ thu hút du khách mà còn tạo ra một hệ sinh thái biển đa dạng và phong phú.

0.5:
gpt4o_response: Một sự thật thú vị về Việt Nam là đất nước này có hang động lớn nhất thế giới, tên là Hang Sơn Đoòng. Hang Sơn Đoòng nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng, tỉnh Quảng Bình. Hang động này được phát hiện vào năm 1991 bởi một người dân địa phương tên là Hồ Khanh, nhưng mãi đến năm 2009, một đoàn thám hiểm người Anh mới chính thức khảo sát và công bố về kích thước khổng lồ của nó. Hang Sơn Đoòng có chiều dài hơn 5 km, cao 200 m và rộng 150 m, đủ lớn để chứa cả một tòa nhà chọc trời 40 tầng. Hang động này còn có hệ sinh thái riêng với rừng cây và sông ngầm, tạo nên một cảnh quan thiên nhiên vô cùng kỳ vĩ và độc đáo.
mini_response: Một sự thật thú vị về Việt Nam là đất nước này có nhiều loại trái cây phong phú và đa dạng. Việt Nam được mệnh danh là "vương quốc trái cây" với nhiều loại trái cây nổi tiếng như xoài, nhãn, vải, sầu riêng, và thanh long. Đặc biệt, trái cây Việt Nam không chỉ ngon mà còn mang nhiều ý nghĩa văn hóa và thường xuất hiện trong các lễ hội, dịp Tết hay các bữa tiệc. Một trong những loại trái cây độc đáo nhất là "sầu riêng", được biết đến với hương vị đặc trưng và mùi hương mạnh mẽ, có thể gây ra tranh cãi giữa những người yêu thích và không thích nó!

1.0:
gpt4o_response: Một sự thật thú vị về Việt Nam là đất nước này là nơi sản xuất và xuất khẩu hạt điều lớn nhất thế giới. Hạt điều Việt Nam được đánh giá cao về chất lượng và được xuất khẩu đến nhiều quốc gia trên toàn cầu. Ngành công nghiệp hạt điều đã trở thành một trong những ngành kinh tế quan trọng, đóng góp đáng kể vào kim ngạch xuất khẩu của Việt Nam.
mini_response: Một sự thật thú vị về Việt Nam là quốc gia này có một trong những bãi biển đẹp nhất thế giới, đó là bãi biển Mỹ Khê, nằm ở thành phố Đà Nẵng. Năm 2005, bãi biển này được tạp chí Forbes bình chọn là một trong sáu bãi biển quyến rũ nhất hành tinh. Với cát trắng mịn, nước biển trong xanh và khí hậu ôn hòa, Mỹ Khê không chỉ thu hút du khách trong nước mà còn nhiều du khách quốc tế đến tham quan và nghỉ dưỡng.

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)
Khi temperature tăng từ 0.0 lên 1.0, nội dung trở nên đa dạng hơn rõ rệt — temperature thấp (0.0, 0.5) cả hai model đều hội tụ về cùng chủ đề (hang Sơn Đoòng, bờ biển), trong khi temperature cao hơn (1.0) sinh ra các chủ đề hoàn toàn khác nhau (hạt điều, bãi Mỹ Khê). Ngoài ra, độ dài và mức độ chi tiết cũng giảm khi temperature tăng, cho thấy model tự tin hơn vào một hướng thay vì liệt kê nhiều thông tin để an toàn.
**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
Nên đặt khoảng 0.2 – 0.3. Chatbot CSKH cần câu trả lời nhất quán, chính xác, và có thể dự đoán được - khách hỏi cùng một câu phải nhận được thông tin giống nhau, không bị sai lệch do tính ngẫu nhiên. Temperature thấp đảm bảo điều đó, đồng thời vẫn đủ linh hoạt để câu văn không cứng nhắc như template.
---

### Bài tập 2.2 — Đánh Đổi Chi Phí
Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**
workload: 10.000 × 3 × 350 = 10,5 triệu token/ngày.
GPT-4o: ~$2.50 / 1M token → 10,5M × $2.50 = ~$26.25/ngày
GPT-4o-mini: ~$0.15 / 1M token → 10,5M × $0.15 = ~$1.58/ngày
→ GPT-4o đắt hơn khoảng ~16–17 lần cho workload này.

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**
GPT-4o xứng đáng hơn: Hệ thống tư vấn pháp lý hoặc hỗ trợ chẩn đoán y tế, một câu trả lời sai có thể gây hậu quả nghiêm trọng, và chất lượng reasoning phức tạp là yếu tố cốt lõi, không thể xem nhẹ chỉ để tiết kiệm chục $/ngày.
GPT-4o-mini phù hợp hơn: Chatbot FAQ cho e-commerce (tra cứu chính sách đổi trả, giờ mở cửa, trạng thái đơn hàng) — câu hỏi đơn giản, có cấu trúc rõ, volume cao, và sai sót nhỏ không gây rủi ro lớn.
---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)
Streaming quan trọng nhất khi response dài và người dùng đang chờ trực tiếp, ví dụ chatbot hội thoại, công cụ viết lách, hay giải thích code, vì người dùng nhận được phản hồi ngay lập tức thay vì nhìn màn hình trống 3–5 giây, giảm đáng kể cảm giác "lag" dù tổng thời gian hoàn thành không đổi. Ngược lại, non-streaming phù hợp hơn khi output cần được xử lý toàn bộ trước khi dùng, ví dụ pipeline tự động hóa parse JSON từ response, batch processing, hay các tác vụ backend không có người dùng chờ trực tiếp, vì streaming trong các trường hợp này chỉ làm phức tạp code mà không mang lại lợi ích UX nào.

## Danh Sách Kiểm Tra Nộp Bài
- [ ] Tất cả tests pass: `pytest tests/ -v`
- [ ] `call_openai` đã triển khai và kiểm thử
- [ ] `call_openai_mini` đã triển khai và kiểm thử
- [ ] `compare_models` đã triển khai và kiểm thử
- [ ] `streaming_chatbot` đã triển khai và kiểm thử
- [ ] `retry_with_backoff` đã triển khai và kiểm thử
- [ ] `batch_compare` đã triển khai và kiểm thử
- [ ] `format_comparison_table` đã triển khai và kiểm thử
- [ ] `exercises.md` đã điền đầy đủ
- [ ] Sao chép bài làm vào folder `solution` và đặt tên theo quy định 
