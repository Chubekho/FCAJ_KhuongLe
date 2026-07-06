---
title: "Event 2"
date: 2026-06-08
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

## Bài thu hoạch sự kiện: FCAJ Community Day (buổi kỹ thuật)

### Vì sao em tham gia sự kiện này

Đây là lần thứ 2 em tham gia sự kiện của FCAJ, và lần này em háo hức hơn hẳn lần đầu vì đã biết trước không khí sẽ như thế nào. Khác với buổi trước thiên về truyền cảm hứng và góc nhìn nghề nghiệp, chương trình lần này công bố hẳn 5 chủ đề rất "nặng đô" về kỹ thuật — toàn những cái tên mới toanh với em như Deep Response Engine, Voice Agent, MCP. Đúng lúc đó em cũng đang loay hoay với phần xử lý bất đồng bộ SQS/Lambda cho dự án workshop của mình, nên nghĩ bụng: thôi thì cứ đi nghe thử, biết đâu lại vỡ ra được điều gì hay ho để áp dụng ngược lại vào project, hoặc ít nhất cũng mở mang thêm một chút về hướng AI đang đi tới đâu ngoài phạm vi mấy bài lab em đang làm.

### Thông tin sự kiện

| Mục | Chi tiết |
| --- | --- |
| Tên sự kiện | FCAJ Community Day |
| Tổ chức bởi | Huỳnh Hoàng Long |
| Địa điểm | Bitexco Financial Tower, 2 Đường Hải Triều, TP. Hồ Chí Minh |
| Thời gian | 08:30 – 11:30, ngày 08/06/2026 |
| Số lượng tham dự | 325 người |

Vẫn là địa điểm quen thuộc trên tầng cao của Bitexco, nhưng lần này không khí có phần "khô khan" hơn buổi trước — ít phần giao lưu mở đầu, vào thẳng nội dung kỹ thuật gần như ngay khi ổn định chỗ ngồi. Có lẽ vì ban tổ chức đã lường trước 5 session dồn dập trong vỏn vẹn 3 tiếng nên không có nhiều thời gian để dềnh dàng.

### Các phần trình bày

Chương trình gồm 5 session kỹ thuật nối tiếp nhau, mỗi phần khoảng 25-30 phút, gần như không có khoảng nghỉ đáng kể giữa các session — cảm giác giống như đang "cày" một khóa học rút gọn hơn là một buổi networking thông thường:

1. **Deep Response Engine** (09:00–09:25) — hệ thống tự phát hiện và tự xử lý sự cố cloud, không cần con người can thiệp.
2. **Voice Agents** (09:25–09:55) — xây dựng trợ lý thoại AI với Amazon Nova Sonic.
3. **AWS DevOps Agent** (09:55–10:20) — "đồng đội vận hành" AI hỗ trợ DevOps 24/7.
4. **AI-Powered Productivity** (10:20–10:45) — ứng dụng AI vào quản lý nhân sự với Amazon Quick.
5. **Secure Private MCP Connection** (10:45–11:30) — kết nối MCP an toàn qua VPC PrivateLink.

### Ghi chú của em cho từng phần

**Về Deep Response Engine:** Phần mở màn này khiến em hơi choáng theo kiểu tích cực. Ý tưởng cốt lõi là để AI tự lo trọn vòng đời của một sự cố — từ lúc phát hiện bất thường, tự truy ra nguyên nhân gốc rễ, cho tới lúc tự sửa — mà không cần ai trực đêm dán mắt vào dashboard. Diễn giả có nhắc tới việc chuyển tư duy vận hành từ "chờ chuông báo động rồi mới nhảy vào" sang "hệ thống tự hành động trước khi con người kịp nhận ra vấn đề". Nghe thì có vẻ hơi viễn tưởng so với thực tế project nhỏ của em (hiện tại em vẫn đang debug kiểu truyền thống — mở CloudWatch Logs, dò từng dòng), nhưng nó cho em thấy rõ một hướng đi trong tương lai: vận hành hệ thống sẽ không còn là công việc "canh màn hình" nữa.

**Về Voice Agents:** Đây có lẽ là phần khiến em ấn tượng nhất về mặt con số. Diễn giả nhấn mạnh ngưỡng độ trễ phải dưới 300 mili-giây thì cuộc hội thoại mới không bị cảm giác "khựng" như đang nói chuyện với máy trả lời tự động ngày xưa. Em chưa từng nghĩ một chi tiết nhỏ như độ trễ lại quan trọng đến mức quyết định cả trải nghiệm người dùng như vậy — với các API thông thường em làm (kiểu chờ vài giây để AI sinh nội dung) thì có vẻ chấp nhận được, nhưng với thoại thời gian thực thì rõ ràng là một bài toán hoàn toàn khác cấp độ, đòi hỏi cả một chuỗi hạ tầng streaming phía sau chứ không đơn giản gọi API rồi đợi.

**Về AWS DevOps Agent:** Phần demo trực tiếp trên ECS là lúc em tập trung nhất trong cả buổi, vì nó gần gũi với công việc thật của em hơn cả. Cảnh agent tự phát hiện một container đang lỗi rồi tự khởi động lại service, không cần ai bấm nút, khiến em bật cười nhớ lại mấy lần mình phải ngồi SSH thủ công vào EC2 lúc nửa đêm chỉ để restart lại một service bị treo. Nếu sau này có công cụ kiểu này áp dụng cho dự án nhỏ như của em thì chắc tiết kiệm được kha khá thời gian "trực chiến" không cần thiết.

**Về AI-Powered Productivity:** Thú thật đây là phần em hiểu ít nhất, vì nội dung thiên hẳn về nghiệp vụ nhân sự (HR) — một mảng hoàn toàn xa lạ với dân kỹ thuật như em. Nhưng đúng là nó mở ra một góc nhìn mới: hóa ra AI bây giờ không chỉ quanh quẩn ở team dev, mà đang len lỏi vào cả những phòng ban tưởng chừng chẳng liên quan gì tới công nghệ như nhân sự hay tài chính. Nghe hơi ngoài chuyên môn nhưng cũng là một lời nhắc rằng phạm vi ứng dụng AI đang rộng hơn em tưởng rất nhiều.

**Về Secure MCP Connection:** Đây là session dài nhất (45 phút) và cũng là phần "cân não" nhất với em trong cả buổi sáng. Về cơ bản, MCP giống như một loại "cổng kết nối vạn năng" giúp AI có thể gọi được vào các công cụ, cơ sở dữ liệu, hệ thống nội bộ của doanh nghiệp thay vì chỉ trả lời chat suông. Vấn đề đau đầu nhất được đặt ra là bảo mật: một khi để AI "chạm" được vào dữ liệu nội bộ, làm sao đảm bảo dữ liệu đó không bị lộ ra ngoài internet công cộng. Giải pháp trình bày là cho MCP server chạy hẳn trong một VPC riêng, kết nối qua PrivateLink — nói cách khác là "nhốt" luồng dữ liệu nhạy cảm lại trong mạng nội bộ của AWS, không cho nó có cơ hội đi lạc ra ngoài. Nội dung khá nâng cao so với trình độ hiện tại của em, có lúc nghe không kịp hiểu hết mọi thuật ngữ, nhưng ít nhất nắm được cái lõi vấn đề và vì sao người ta phải làm phức tạp như vậy thay vì để AI gọi thẳng ra internet cho tiện.

### Điều em rút ra được

* Tư duy "action-driven thay vì alert-driven" là thứ em thấy đáng suy nghĩ nhất buổi hôm đó — thay vì chỉ dựng cảnh báo rồi ngồi chờ có chuyện mới nhảy vào xử lý, hoàn toàn có thể tính tới việc để hệ thống tự xử lý sẵn một số lỗi lặp đi lặp lại quen thuộc, đỡ tốn công người.
* Độ trễ (latency) hóa ra là một yếu tố sống còn không kém gì độ chính xác khi làm bất cứ thứ gì liên quan tới AI theo thời gian thực — không riêng gì thoại, mà bất kỳ trải nghiệm tương tác trực tiếp nào với người dùng cũng cần để tâm tới con số này.
* MCP là khái niệm em ghi chú lại để tìm hiểu sâu hơn sau này, vì nó chạm tới một hướng rất thú vị: để AI thực sự "làm việc" được trong hệ thống thật thay vì chỉ ngồi chat — dù hiện tại dự án của em chưa cần dùng tới mức đó.
* Nhìn rộng ra, cả 5 session đều xoay quanh một chủ đề chung: AI đang dần chuyển từ vai trò "trả lời câu hỏi" sang vai trò "tự đưa ra hành động" trong hệ thống thật — một xu hướng mà chắc chắn vài năm tới em sẽ còn gặp lại nhiều lần nữa trong công việc.

### Cảm nhận chung

So với buổi FCAJ lần trước em tham gia, lần này đậm chất kỹ thuật hơn hẳn, tốc độ trình bày cũng dồn dập hơn nên có những đoạn em không theo kịp hết, đặc biệt là phần MCP ở cuối khi đầu óc đã hơi "quá tải" sau 4 session liên tục trước đó. Nhưng nhìn lại thì đây vẫn là một buổi sáng đáng giá — được nghe trực tiếp những công nghệ mới nhất mà nếu tự mày mò tài liệu một mình chắc phải mất rất nhiều thời gian mới biết tới, chưa kể được ngồi giữa một cộng đồng toàn những người cùng quan tâm tới AWS như mình cũng là một trải nghiệm khá thú vị theo cách riêng của nó.

### Một số hình ảnh khi tham gia sự kiện

> ![Hình ảnh tại sự kiện](/images/4-Events/4.2-Event2/photo1.jpg)
>
> ![Hình ảnh tại sự kiện](/images/4-Events/4.2-Event2/photo2.jpg)