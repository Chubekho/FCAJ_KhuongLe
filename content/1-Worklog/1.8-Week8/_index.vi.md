---
title: "Worklog Tuần 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:
* Tìm hiểu nhóm dịch vụ Security & Reliability: giới hạn quyền, bảo vệ ứng dụng, mã hóa dữ liệu, backup hệ thống.
* Làm quen với Infrastructure as Code (IaC) qua AWS CloudFormation — thay vì thao tác tay trên Console.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu IAM Permission Boundary: giới hạn quyền tối đa mà một User/Role có thể có, dù policy gắn thêm là gì. <br> - **Thực hành:** Tạo Permission Boundary, gán cho IAM User, kiểm chứng user không thể tự leo thang quyền vượt boundary. | 08/06/2026 | 08/06/2026 | [Giới hạn quyền User với IAM Permission Boundary](https://000030.awsstudygroup.com) |
| 3 | - Tìm hiểu AWS WAF: bảo vệ ứng dụng web khỏi các lỗ hổng phổ biến (SQL Injection, XSS), rate limiting. <br> - **Thực hành:** Gắn WAF WebACL vào Application Load Balancer, tạo rule chặn SQL Injection và giới hạn request rate. | 09/06/2026 | 09/06/2026 | [Bảo vệ Ứng dụng và API với AWS WAF](https://000026.awsstudygroup.com) |
| 4 | - Tìm hiểu AWS KMS: quản lý encryption key, envelope encryption. <br> - **Thực hành:** Tạo Customer Managed Key, mã hóa một object trong S3 bằng key riêng thay vì key mặc định của AWS. | 10/06/2026 | 10/06/2026 | [Quản lý Khóa Mã hóa với AWS KMS](https://000033.awsstudygroup.com) |
| 5 | - Tìm hiểu AWS Backup: backup plan tự động, retention policy. <br> - **Thực hành:** Tạo Backup Plan tự động backup RDS hàng ngày, thực hiện thử restore từ bản backup. | 11/06/2026 | 11/06/2026 | [Triển khai Kế hoạch Backup Hệ thống với AWS Backup](https://000013.awsstudygroup.com) |
| 6 | - Tìm hiểu AWS CloudFormation: Infrastructure as Code, template YAML/JSON, khái niệm Stack. <br> - **Thực hành:** Viết template tạo VPC + EC2 bằng CloudFormation, so sánh với việc thao tác tay trên Console. | 12/06/2026 | 12/06/2026 | [Khởi tạo Infrastructure as Code với AWS CloudFormation](https://000037.awsstudygroup.com) |

### Kết quả đạt được tuần 8:
* Hiểu và áp dụng được nguyên tắc least-privilege ở tầng sâu hơn IAM Policy thông thường:
  * Permission Boundary giới hạn "trần" quyền tối đa, ngăn escalation dù ai đó vô tình gắn thêm policy quá rộng.
* Triển khai được lớp bảo vệ ứng dụng ở tầng network với AWS WAF:
  * Hiểu cơ chế managed rule (chặn exploit phổ biến) kết hợp custom rule (rate limiting riêng theo nhu cầu).
* Nắm vững khái niệm mã hóa dữ liệu với KMS:
  * Phân biệt AWS managed key và Customer managed key — khi nào cần kiểm soát riêng vòng đời của key.
* Xây dựng được chiến lược backup tự động thay vì backup thủ công:
  * Hiểu retention policy và tầm quan trọng của việc test restore định kỳ (backup không test = không đáng tin).
* Làm quen với tư duy Infrastructure as Code:
  * Hạ tầng được định nghĩa bằng file, có thể version control, review, tái sử dụng — khác hẳn thao tác tay dễ sai sót và khó tái lập.
  * Đây là nền tảng tư duy quan trọng cho việc quản lý hạ tầng dự án tốt nghiệp ở các tuần sau, dù công cụ IaC cụ thể có thể khác (scripts/CLI thay vì CloudFormation).