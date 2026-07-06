---
title: "Worklog Tuần 3"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:
* Hoàn tất việc lấy Credit từ chương trình AWS Free Tier.
* Thiết lập cảnh báo chi phí và áp dụng các tiêu chuẩn bảo mật tài khoản cao nhất (IAM User, MFA).
* Mở rộng hiểu biết về IAM: từ việc cấp quyền cho con người (User) sang cấp quyền trực tiếp cho tài nguyên AWS (Role) — nền tảng bảo mật quan trọng sẽ áp dụng thực tế ở tuần sau.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 3 | - **Thực hành Task 3 (Credit):** Khởi tạo S3 Bucket tĩnh. <br> - **Thực hành Task 4 (Credit):** Tạo Database RDS cơ bản. <br> - **Thực hành Task 5 (Credit):** Tạo hàm Lambda đơn giản. | 05/05/2026 | 05/05/2026 | [AWS Free Tier Guide](https://000001.awsstudygroup.com/vi/) |
| 5 | - Thực hành quản lý mức chi phí sử dụng AWS với dịch vụ AWS Budgets. <br> - Quản trị quyền truy cập bằng AWS IAM (Tạo Group và Admin User). <br> - Thiết lập bảo mật cho IAM User (Password Policy, MFA). | 07/05/2026 | 07/05/2026 | [AWS Budgets](https://000007.awsstudygroup.com/vi/) <br> [AWS IAM](https://000002.awsstudygroup.com/vi/) |
| 7 | - Tìm hiểu rủi ro của việc lưu Access Key/Secret Key ở dạng cứng (hardcoded) trên server hoặc trong source code. <br> - Tìm hiểu khái niệm IAM Role: cấp quyền trực tiếp cho AWS resource thay vì gán static credentials. <br> - **Thực hành:** Tạo một IAM Role cho phép truy cập S3, tìm hiểu cơ chế cấp quyền tạm thời (temporary credentials) đứng sau Instance Profile. | 09/05/2026 | 09/05/2026 | [AWS IAM](https://000002.awsstudygroup.com/vi/) |

### Kết quả đạt được tuần 3:
* Hoàn thành trọn vẹn 5 "Money-Making" Tasks, chính thức thu thập đủ toàn bộ $200 Credit để sử dụng cho các bài Lab nâng cao:
  * S3: hiểu khái niệm object storage, bucket, cách upload/quản lý object cơ bản.
  * RDS: khởi tạo instance database và kiểm tra kết nối cơ bản.
  * Lambda: viết và deploy một function đơn giản, hiểu mô hình serverless (không cần quản lý server).
* Đã thiết lập cảnh báo chi phí bằng AWS Budgets:
  * Cấu hình ngưỡng cảnh báo theo % ngân sách dự kiến.
  * Kết nối email nhận thông báo khi vượt ngưỡng, tránh phát sinh chi phí ngoài ý muốn.
* Đã thiết lập thành công tài khoản AWS an toàn với IAM Admin User (ngừng dùng tài khoản Root):
  * Tạo IAM Group phân quyền theo vai trò thay vì gán quyền lẻ tẻ cho từng User.
  * Áp dụng Password Policy bắt buộc đổi mật khẩu ở lần đăng nhập đầu.
  * Kích hoạt MFA (Virtual MFA Device) cho tài khoản Admin.
* Hiểu vì sao lưu Access Key/Secret Key cứng là một rủi ro bảo mật lớn:
  * Rủi ro thực tế: lộ key qua commit Git, log ứng dụng, hoặc file cấu hình public.
  * Giải pháp: dùng IAM Role để cấp quyền tạm thời (temporary credentials), tự động xoay vòng, không cần lưu trữ tĩnh trên resource — kiến thức sẽ áp dụng thực tế khi deploy EC2 ở tuần 4.