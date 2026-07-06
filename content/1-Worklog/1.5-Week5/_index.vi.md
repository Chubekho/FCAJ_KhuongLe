---
title: "Worklog Tuần 5"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:
* Hoàn tất các dịch vụ nền tảng còn lại trong nhóm "Khám phá dịch vụ AWS": lưu trữ tĩnh với S3, cơ sở dữ liệu quản lý với RDS, giám sát hệ thống với CloudWatch và tự động mở rộng với EC2 Auto Scaling.
* Thực hành kết nối Hybrid Cloud (giả lập on-premise ↔ cloud) thông qua VPC Endpoint và DNS Resolver.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu Amazon S3: object storage, storage class, versioning. <br> - **Thực hành:** Tạo bucket, bật Static Website Hosting, cấu hình Bucket Policy public-read, deploy một trang HTML tĩnh và truy cập qua endpoint S3. | 18/05/2026 | 18/05/2026 | [Hosting static website với Amazon S3](https://000057.awsstudygroup.com/vi/) |
| 3 | - Tìm hiểu Amazon RDS: managed relational database, so sánh với tự vận hành DB trên EC2 (backup, patching, Multi-AZ). <br> - **Thực hành:** Khởi tạo RDS PostgreSQL instance trong Private Subnet, cấu hình Security Group để chỉ EC2 trong VPC truy cập được. | 19/05/2026 | 19/05/2026 | [Tạo cơ sở dữ liệu trên Amazon Relational Database Service (Amazon RDS)](https://000005.awsstudygroup.com/vi/) |
| 4 | - Tìm hiểu Amazon CloudWatch: Metrics, Logs, Alarms, Dashboard. <br> - **Thực hành:** Tạo CloudWatch Alarm theo dõi CPUUtilization của EC2, kết nối SNS Topic để nhận cảnh báo qua email khi vượt ngưỡng. | 20/05/2026 | 20/05/2026 | [Tạo bảng theo dõi hệ thống với Amazon Cloudwatch](https://000008.awsstudygroup.com/vi/) |
| 5 | - Tìm hiểu EC2 Auto Scaling: Launch Template, Auto Scaling Group (ASG), Target Tracking Policy. <br> - **Thực hành:** Tạo Launch Template từ AMI có sẵn, tạo ASG scale theo % CPU trung bình, kiểm tra hành vi scale-out/scale-in. | 21/05/2026 | 21/05/2026 | [Tự động mở rộng qui mô ứng dụng với Amazon EC2 Autoscaling](https://000006.awsstudygroup.com/vi/) |
| 6 | - Thực hành lab **"Đảm bảo truy cập Hybrid an toàn đến S3 bằng VPC Endpoint"**: dựng 2 VPC (Cloud & On-Prem), tạo Gateway Endpoint và Interface Endpoint tới S3, mô phỏng kết nối Site-to-Site VPN, kiểm tra resolve DNS từ phía on-prem. | 22/05/2026 | 22/05/2026 | [Thiết lập Hybrid DNS với Route 53 Resolver](https://000010.awsstudygroup.com/vi/) |

### Kết quả đạt được tuần 5:
* Triển khai thành công một static website trên S3:
  * Hiểu rõ cơ chế phân quyền Bucket Policy khác với quyền IAM User/Role như thế nào.
* Khởi tạo và kết nối thành công RDS PostgreSQL từ EC2 trong cùng VPC:
  * Hiểu lý do nên đặt Database trong Private Subnet thay vì Public Subnet để giảm bề mặt tấn công.
* Thiết lập được luồng giám sát cơ bản: CloudWatch Alarm → SNS → Email:
  * Hiểu vai trò của observability trong vận hành production thay vì chỉ kiểm tra thủ công.
* Hiểu và thực hành được cơ chế Auto Scaling:
  * Hệ thống tự thêm/bớt instance theo tải thực tế, tránh lãng phí tài nguyên lúc thấp điểm và tránh quá tải lúc cao điểm.
* Hoàn thành lab VPC Endpoint/Hybrid DNS:
  * Phân biệt Gateway Endpoint (định tuyến qua route table, dùng cho S3/DynamoDB) và Interface Endpoint (dùng ENI + PrivateLink, dùng cho phần lớn dịch vụ AWS còn lại).
  * Hiểu cách một trung tâm dữ liệu on-premise có thể truy cập private vào S3 mà không đi qua Internet công cộng.
* Bắt đầu hình dung rõ hơn các thành phần này sẽ được dùng thế nào trong một hệ thống production thực tế (S3 lưu file, RDS lưu dữ liệu, Auto Scaling + CloudWatch cho tầng ứng dụng) — nền tảng cho việc thiết kế hạ tầng dự án tốt nghiệp ở các tuần sau.