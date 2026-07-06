---
title: "Worklog Tuần 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:
* Tìm hiểu kiến trúc Serverless: Lambda tương tác trực tiếp với S3 và DynamoDB, không cần server chạy nền liên tục.
* Xây dựng REST API bằng API Gateway để expose Lambda ra bên ngoài.
* Thực hành xử lý bất đồng bộ (async) với SQS và SNS — mô hình decouple producer/consumer.
* Làm quen với observability cho hệ Serverless: CloudWatch và X-Ray, cùng cách tự động hoá deploy bằng CodePipeline.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu kiến trúc Serverless: Lambda, trigger từ S3 Event, đọc/ghi dữ liệu vào DynamoDB. <br> - **Thực hành:** Viết Lambda function tự động xử lý khi có file mới upload lên S3, ghi kết quả vào DynamoDB. | 01/06/2026 | 01/06/2026 | [Serverless - Lambda tương tác với S3 và DynamoDB](https://000078.awsstudygroup.com/) |
| 3 | - Tìm hiểu Amazon API Gateway: REST API, Lambda Proxy Integration, request/response mapping. <br> - **Thực hành:** Xây REST API expose Lambda function ra ngoài, test bằng Postman và một frontend đơn giản. | 02/06/2026 | 02/06/2026 | [Serverless - Xây dựng Frontend gọi API Gateway](https://000079.awsstudygroup.com/) |
| 4 | - Tìm hiểu xử lý bất đồng bộ với Amazon SQS (queue) và SNS (pub/sub, fan-out). <br> - **Thực hành:** Mô phỏng luồng xử lý đơn hàng — API đẩy message vào SQS, Lambda worker consume và xử lý, SNS gửi thông báo kết quả cho các subscriber. | 03/06/2026 | 03/06/2026 | [Serverless - Xử lý đơn hàng với SQS và SNS](https://000083.awsstudygroup.com/) |
| 5 | - Tìm hiểu observability cho hệ Serverless: CloudWatch Logs/Metrics và AWS X-Ray (distributed tracing). <br> - **Thực hành:** Bật X-Ray cho Lambda, theo dõi latency từng bước trong chuỗi API Gateway → Lambda → DynamoDB. | 04/06/2026 | 04/06/2026 | [Serverless - Giám sát ứng dụng Serverless với CloudWatch và X-Ray](https://000085.awsstudygroup.com/) |
| 6 | - Tìm hiểu CI/CD riêng cho ứng dụng Serverless (khác cách deploy container ở tuần 6) — dùng AWS SAM/CloudFormation để đóng gói và deploy Lambda. <br> - **Thực hành:** Dựng pipeline CodePipeline tự động deploy lại Lambda function mỗi khi có commit mới. | 05/06/2026 | 05/06/2026 | [Serverless - CI/CD với AWS CodePipeline](https://000084.awsstudygroup.com/) |

### Kết quả đạt được tuần 7:
* Hiểu và thực hành thành thạo mô hình Serverless "event-driven":
  * Lambda được trigger tự động bởi S3 Event, không cần polling hay server chạy nền.
  * Đọc/ghi dữ liệu vào DynamoDB (NoSQL) từ trong Lambda function.
* Xây dựng thành công REST API với API Gateway:
  * Hiểu cơ chế Lambda Proxy Integration — API Gateway chuyển thẳng request/response cho Lambda xử lý.
* Nắm vững mô hình xử lý bất đồng bộ với SQS và SNS:
  * SQS: hàng đợi tin nhắn (queue), decouple giữa nơi tạo request và nơi xử lý — nếu consumer bị chậm/lỗi, request vẫn an toàn trong queue chứ không mất.
  * SNS: cơ chế pub/sub, một message có thể "fan-out" gửi tới nhiều subscriber cùng lúc (email, Lambda khác, SQS khác...).
  * Đây chính là mô hình async job processing (API trả về ngay, xử lý thật diễn ra ở background) — kiến trúc lõi sẽ áp dụng trực tiếp cho phần xử lý bất đồng bộ ở dự án workshop.
* Thiết lập được observability cho hệ Serverless:
  * CloudWatch Logs để debug lỗi runtime của Lambda.
  * X-Ray để trace toàn bộ đường đi của 1 request qua nhiều service (API Gateway → Lambda → DynamoDB), xác định chính xác bước nào đang chậm.
* Xây dựng pipeline CI/CD riêng cho Serverless:
  * Hiểu sự khác biệt so với CI/CD container ở tuần 6: Serverless deploy qua SAM/CloudFormation (đóng gói code + config hạ tầng), không cần build Docker image.