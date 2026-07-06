---
title: "Event 1"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

## Bài thu hoạch sự kiện: FCAJ Community Day

### Vì sao em tham gia sự kiện này

Trong lúc đang học các dịch vụ AWS theo lộ trình FCAJ, em thấy trên nhóm cộng đồng có thông báo về buổi FCAJ Community Day — quy tụ nhiều bạn cũng đang học và làm việc với AWS ở Việt Nam. Em đăng ký tham gia với mục đích chính là nghe thêm góc nhìn thực tế từ người đã đi làm, thay vì chỉ học qua tài liệu.

### Thông tin sự kiện

| Mục | Chi tiết |
| --- | --- |
| Tên sự kiện | FCAJ Community Day |
| Tổ chức bởi | Huỳnh Hoàng Long, Thien Lu & Trần Đại Vĩ |
| Địa điểm | Tầng 26, Bitexco Financial Tower, 2 Đường Hải Triều, TP. Hồ Chí Minh |
| Thời gian | 08:30 – 12:00, ngày 23/05/2026 |
| Số lượng tham dự | 399 người |

Điểm em thấy khác so với các buổi hội thảo công nghệ thông thường: người thuyết trình không phải chuyên gia mời từ bên ngoài, mà chính là các bạn/anh chị trong cộng đồng — vừa mới đi làm, vừa từng là học viên như tụi em. Nghe cảm giác gần gũi và dễ tin hơn.

### Các phần trình bày trong buổi sáng

Chương trình gồm 6 phần chia đều trong 3 tiếng:

1. **Context Is Everything** — vì sao AI trả lời tệ, và cách cải thiện bằng cách cho AI đủ ngữ cảnh.
2. **Amazon QuickSight Q** — trợ lý AI hỏi-đáp dữ liệu bằng ngôn ngữ tự nhiên, không cần biết SQL.
3. **CloudFront: từ Edge tới Origin** — CloudFront không chỉ là CDN mà còn xử lý bảo mật, tối ưu chi phí, tăng tốc độ.
4. **36 giờ làm hackathon LotusHacks** — hành trình build sản phẩm UTMorpho từ ý tưởng tới demo.
5. **Vì sao "Deterministic" LLM vẫn không deterministic** — hiểu lầm phổ biến về Temperature=0.
6. **Multi-Agent System chấm điểm tín dụng startup** — case study dùng nhiều AI Agent phối hợp thay vì 1 agent làm hết.

### Ghi chú của em cho từng phần

**Về Context cho AI:** Phần này giúp em hiểu ra 1 điều khá cơ bản nhưng trước giờ em ít để ý — AI trả lời dở không phải vì AI yếu, mà thường là vì mình hỏi thiếu thông tin. Diễn giả có nhắc tới việc nên xây dựng dần một kiểu "bộ nhớ ngữ cảnh" riêng, thay vì lần nào cũng giải thích lại từ đầu cho AI.

**Về QuickSight Q:** Em ấn tượng nhất ở việc có thể tạo dashboard chỉ bằng cách mô tả bằng lời, AI tự chọn loại biểu đồ phù hợp. Với người không rành SQL như em thì đây là tính năng khá thiết thực.

**Về CloudFront:** Trước giờ em chỉ nghĩ CloudFront đơn giản là "cái cache cho web nhanh hơn". Sau buổi này em mới biết nó còn gánh luôn phần bảo mật (WAF, Shield, chặn theo khu vực địa lý) và có cơ chế riêng để khóa S3 chỉ cho CloudFront truy cập (gọi là OAC) — khá liên quan tới phần hạ tầng em đang làm ở dự án của mình.

**Về hackathon 36 giờ:** Phần này không nặng kỹ thuật mà thiên về kinh nghiệm làm việc nhóm. Điều em nhớ nhất là chuyện nhóm đó chấp nhận bỏ bớt 2 tính năng lớn khi gần hết giờ để giữ bản demo chạy ổn định — thà thiếu tính năng còn hơn demo bị lỗi.

**Về LLM không deterministic:** Đây là phần khiến em bất ngờ nhất, vì em từng nghĩ đặt Temperature=0 thì AI sẽ luôn trả lời giống hệt nhau mỗi lần. Hóa ra không phải vậy — do cách tính toán trên phần cứng (GPU) và cách hệ thống chia nhỏ model ra nhiều máy để xử lý, kết quả vẫn có thể lệch nhau chút ít dù cùng một câu hỏi.

**Về Multi-Agent chấm tín dụng:** Bài toán đặt ra là các startup thường khó vay vốn vì ngân hàng không có đủ dữ liệu để đánh giá. Giải pháp dùng nhiều AI Agent, mỗi agent phụ trách một mảng riêng (thu thập dữ liệu, phân tích tài chính, đánh giá thị trường...) rồi tổng hợp lại — thay vì bắt 1 agent ôm hết mọi việc.

### Điều em rút ra được

Nhìn chung buổi này giúp em có thêm vài điều để áp dụng ngay cho việc học và làm dự án của mình:

* Khi dùng AI để hỗ trợ code hay viết tài liệu, nên mô tả kỹ ngữ cảnh (đang làm gì, dùng công nghệ gì, ràng buộc ra sao) thay vì hỏi cộc lốc — chất lượng câu trả lời sẽ khác hẳn.
* CloudFront không chỉ để tăng tốc mà còn là lớp bảo mật đầu tiên chắn trước hệ thống — điều này liên quan trực tiếp tới việc lựa chọn CDN cho dự án workshop của em sau này.
* Không nên mặc định kết quả AI luôn ổn định giống nhau — nếu hệ thống của mình phụ thuộc vào AI, cần có bước kiểm tra lại kết quả trước khi dùng.
* Làm sản phẩm thật (dù chỉ là bài tập/dự án nhỏ) thì việc biết dừng đúng lúc, giữ cho phần lõi chạy ổn định quan trọng hơn cố nhồi nhét thêm tính năng.

### Cảm nhận chung

Đây là lần đầu em tham gia một sự kiện cộng đồng công nghệ với quy mô đông như vậy. Điều em thích nhất không hẳn là nội dung chuyên môn (vì một số phần khá nâng cao, em chưa hiểu hết), mà là cảm giác được ngồi giữa rất nhiều người cũng đang học AWS giống mình — thấy đỡ cô đơn hơn hẳn so với việc tự học một mình ở nhà.

### Một số hình ảnh khi tham gia sự kiện

> ![Hình ảnh tại sự kiện](/images/4-Events/4.1-Event1/photo1.jpg)
>
> ![Hình ảnh tại sự kiện](/images/4-Events/4.1-Event1/photo2.jpg)
>
> ![Hình ảnh tại sự kiện](/images/4-Events/4.1-Event1/photo3.jpg)
>
> ![Hình ảnh tại sự kiện](/images/4-Events/4.1-Event1/photo4.jpg)