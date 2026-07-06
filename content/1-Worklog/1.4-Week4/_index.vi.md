---
title: "Worklog Tuần 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:
* Nắm vững kiến thức định tuyến IP và tự tay triển khai hạ tầng mạng ảo chuẩn doanh nghiệp trên Amazon VPC.
* Triển khai máy chủ ứng dụng (EC2) vào chính VPC vừa dựng, áp dụng IAM Role đã học ở tuần 3 để cấp quyền truy cập S3 một cách an toàn.
* Làm quen với môi trường lập trình đám mây AWS Cloud9, chuẩn bị công cụ cho các tuần thực hành tiếp theo.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 3 | - Tìm hiểu lý thuyết về Classless Inter-Domain Routing (CIDR) và Subnet Mask. <br> - Phân tích kỹ thuật chia mạng con Variable Length Subnet Mask (VLSM). | 12/05/2026 | 12/05/2026 | [Giới thiệu Amazon VPC](https://000003.awsstudygroup.com/vi/1-introduce/) |
| 5 | - Thực hành: Khởi tạo Amazon VPC mới (không dùng Default VPC). <br> - Thiết lập Public Subnet và Private Subnet dựa trên tính toán VLSM. <br> - Cấu hình Internet Gateway (IGW) và Route Tables để thông luồng mạng ra internet. | 14/05/2026 | 14/05/2026 | [Chuẩn bị Môi trường](https://000003.awsstudygroup.com/vi/3-prerequisite/)|
| 6 | - **Thực hành:** Khởi tạo EC2 instance trong Public Subnet của VPC vừa tạo. <br> - Kết nối SSH vào máy chủ bằng Keypair (.pem), xử lý phân quyền file chứng chỉ (chmod 400). | 15/05/2026 | 15/05/2026 | [Triển khai Amazon EC2 Instance](https://000003.awsstudygroup.com/vi/4-createec2server/) |
| 7 | - **Thực hành:** Gắn IAM Role đã tạo ở tuần 3 vào EC2 instance (Instance Profile), kiểm chứng EC2 truy cập được S3 mà không cần khai báo Access Key/Secret Key. <br> - Tìm hiểu và thiết lập môi trường lập trình Cloud IDE với AWS Cloud9. | 16/05/2026 | 16/05/2026 | [Cấp quyền cho ứng dụng truy cập dịch vụ AWS thông qua IAM Role](https://000048.awsstudygroup.com/vi/) |

### Kết quả đạt được tuần 4:
* Hiểu sâu về cách thức quy hoạch IP:
  * Phân biệt rõ Network ID và Host ID thông qua dải CIDR.
  * Tính toán VLSM để chia subnet với kích thước khác nhau, tránh lãng phí dải IP.
* Thiết kế và triển khai một Amazon VPC riêng biệt hoàn chỉnh:
  * Public Subnet (có route ra Internet qua IGW) và Private Subnet (cô lập, không route trực tiếp ra ngoài).
  * Route Table riêng cho từng loại subnet, hiểu rõ cơ chế định tuyến phân tách vùng public/private.
* Khởi tạo và đưa máy chủ EC2 hoạt động thành công bên trong VPC vừa thiết lập:
  * Kết nối SSH bằng Keypair, xử lý lỗi permission phổ biến khi dùng file .pem (chmod 400).
* Áp dụng thành công IAM Role (Instance Profiling) vào EC2 thật:
  * Gắn Role trực tiếp cho EC2, xác nhận truy cập S3 bình thường dù không có Access/Secret Key nào lưu trên máy.
  * Kiểm chứng lại lý thuyết bảo mật đã học ở tuần 3 bằng thực hành cụ thể — không còn là lý thuyết suông.
* Khởi tạo thành công môi trường lập trình AWS Cloud9:
  * Viết và chạy lệnh trực tiếp trên trình duyệt, không cần cài môi trường local — sẵn sàng cho các bài thực hành code ở tuần sau.