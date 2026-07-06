---
title: "Worklog Tuần 11"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

- Hoàn thiện các tính năng frontend còn lại: xuất file, quản lý chiến dịch, theo dõi mức sử dụng.
- Nâng cấp bảo mật và khả năng quan sát hệ thống (Secrets Manager, CloudWatch, WAF) trước khi đưa lên môi trường thật.
- Bắt đầu triển khai hạ tầng AWS thật cho dự án workshop: đóng gói artifact và dựng những thành phần hạ tầng đầu tiên.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- |
| 2   | - Xây dựng khu vực xuất file: 3 định dạng PDF/DOCX/HTML, tải trực tiếp qua presigned URL. <br> - Hoàn thiện trang quản lý Chiến dịch (Campaign): tạo mới, gắn nội dung vào chiến dịch, lưu trữ (xóa mềm). <br> - Hoàn thiện trang theo dõi mức sử dụng: thanh tiến trình token/hạn mức, breakdown theo từng model AI.                                                                                                                                                                                                                                       | 29/06/2026   | 29/06/2026      |
| 3   | - Chuyển toàn bộ secret nhạy cảm (JWT, database, API key AI) từ file cấu hình sang dịch vụ quản lý secret tập trung, có cơ chế bật/tắt linh hoạt giữa môi trường local và production. <br> - Chuyển đổi nhà cung cấp AI sang phương án chi phí thấp hơn thông qua lớp trừu tượng hoá provider (dễ dàng đổi lại nếu cần). <br> - Thiết lập hệ thống giám sát log tập trung (log group riêng cho API và Worker), cấu hình cảnh báo qua email khi có lỗi bất thường. <br> - Khởi tạo Web Application Firewall bảo vệ ứng dụng khỏi các cuộc tấn công phổ biến. | 30/06/2026   | 30/06/2026      |
| 4   | - Đóng gói ứng dụng thành các artifact sẵn sàng triển khai: bundle mã nguồn cho tiến trình xử lý nền, build Docker image nhiều giai đoạn (multi-stage) cho tầng API. <br> - Tăng cường cấu hình bảo mật/production cho ứng dụng (proxy, logging format phù hợp môi trường thật). <br> - Build bản production cho frontend, chuẩn bị script triển khai tự động.                                                                                                                                                                                              | 01/07/2026   | 01/07/2026      |
| 5   | - **Bắt đầu triển khai hạ tầng AWS thật:** dựng mạng ảo riêng (nhiều vùng khả dụng), cơ sở dữ liệu quan hệ chế độ dự phòng tự động (Multi-AZ), registry lưu trữ image, các vai trò phân quyền theo nguyên tắc tối thiểu. <br> - Khởi tạo bộ cân bằng tải và nhóm tự động mở rộng cho tầng ứng dụng, cùng dịch vụ cache trong bộ nhớ cho tầng dữ liệu.                                                                                                                                                                                                       | 02/07/2026   | 02/07/2026      |

### Kết quả đạt được tuần 11:

- Hoàn thiện toàn bộ tính năng còn lại ở phía frontend:
  - Người dùng xuất được nội dung ra file thật (PDF/DOCX/HTML) và tổ chức nội dung theo từng chiến dịch marketing.
  - Có cái nhìn rõ ràng về mức tiêu thụ AI theo tháng — quan trọng cho mô hình SaaS tính phí theo usage.
- Nâng cấp đáng kể tầng bảo mật của hệ thống trước khi lên production:
  - Không còn secret nào nằm trực tiếp trong file cấu hình — giảm hẳn rủi ro lộ thông tin nhạy cảm qua source code.
  - Có lớp trừu tượng hoá cho AI Provider — đổi nhà cung cấp AI chỉ bằng 1 biến cấu hình, không phải sửa code nghiệp vụ.
- Thiết lập được lớp quan sát hệ thống (observability) và phòng thủ ở tầng mạng:
  - Log tập trung theo từng thành phần, cảnh báo chủ động thay vì phải tự kiểm tra thủ công.
  - WAF chặn trước các kiểu tấn công phổ biến ngay ở tầng vào của hệ thống.
- Chính thức bước sang giai đoạn triển khai hạ tầng thật:
  - Đóng gói được artifact chuẩn (container image, bundle serverless) — đúng kỹ năng đã luyện tập ở tuần 6-7.
  - Dựng thành công phần khung hạ tầng nền tảng (mạng riêng nhiều vùng khả dụng, database dự phòng, load balancer, auto scaling) — áp dụng trực tiếp kiến thức Highly Availability đã học ở tuần 5.
