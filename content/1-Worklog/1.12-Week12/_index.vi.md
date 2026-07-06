---
title: "Worklog Tuần 12"
date: 2024-01-01
weight: 12
chapter: false
pre: " <b> 1.12 </b> "

---

### Mục tiêu tuần 12:
* Hoàn tất triển khai hạ tầng AWS thật, xây dựng CI/CD tự động và hoàn thiện toàn bộ tài liệu.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành |
| --- | --- | --- | --- |
| 2 | - Xử lý các lỗi phát sinh khi đưa hệ thống lên môi trường thật: quyền IAM còn thiếu, kết nối mã hoá tới database chưa được cấu hình đúng. <br> - Hoàn tất triển khai tiến trình xử lý nền (Worker) dưới dạng serverless, kết nối hàng đợi tin nhắn production. <br> - Xử lý phương án thay thế cho CDN chính (do tài khoản chưa xác minh): chuyển sang lưu trữ tĩnh + CDN thay thế, cấu hình tên miền phụ, gắn Web Application Firewall và cảnh báo giám sát đầy đủ. <br> - Xoay vòng lại toàn bộ secret nhạy cảm từng bị lộ (khoá xác thực, thông tin database, API key AI). <br> - Chạy dữ liệu khởi tạo (seed data) lên production qua đường hầm quản lý phiên an toàn. | 06/07/2026 | 06/07/2026 |
| 3 | - Xây dựng pipeline CI/CD tự động với GitHub Actions: xác thực AWS qua OIDC (không dùng access key dài hạn), tự động kiểm tra code (lint + type-check), build/đẩy image, cập nhật tiến trình nền, build/đẩy frontend rồi kiểm tra sức khoẻ hệ thống. Xác minh thực tế: push code → toàn bộ pipeline chạy xanh → production tự động cập nhật. <br> - Hoàn thành kiểm thử toàn luồng nghiệp vụ trên môi trường thật (đăng ký → persona → tạo nội dung → export → usage), xác nhận WAF chặn tấn công đúng. <br> - Vẽ sơ đồ kiến trúc tổng thể hệ thống. <br> - Rà soát và hoàn thiện README (kiến trúc, hướng dẫn triển khai, sửa các phần không còn khớp thực tế sau khi đổi phương án CDN/xác thực), tổng hợp tài liệu chuẩn bị demo cuối khoá. | 07/07/2026 | 07/07/2026 |

### Kết quả đạt được tuần 12:
* Hoàn tất toàn bộ hạ tầng production cho dự án workshop:
  * Xử lý dứt điểm các lỗi "chỉ xuất hiện trên môi trường thật" (quyền IAM, mã hoá kết nối database) — kinh nghiệm quan trọng: môi trường local/LocalStack không mô phỏng 100% hành vi thật của AWS.
  * Có phương án dự phòng hợp lý khi dịch vụ CDN chính bị chặn — không để một giới hạn ngoài ý muốn làm đình trệ tiến độ.
* Khắc phục triệt để vấn đề bảo mật: toàn bộ secret từng bị lộ đã được xoay vòng, không còn giá trị sử dụng cũ nào tồn tại.
* Xây dựng thành công pipeline CI/CD hoàn chỉnh, không cần thao tác tay: từ lúc push code tới lúc production cập nhật là hoàn toàn tự động, xác thực an toàn không cần lưu access key dài hạn.
* Hoàn thành kiểm thử toàn luồng nghiệp vụ trên môi trường thật — xác nhận hệ thống hoạt động đúng như thiết kế từ đầu đến cuối.
* Hoàn thiện tài liệu kỹ thuật (README, sơ đồ kiến trúc) trong quỹ thời gian gấp rút — tổng kết lại hành trình 4 tuần xây dựng dự án workshop.