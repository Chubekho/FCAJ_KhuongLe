---
title: "Worklog Tuần 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:
* Xây dựng khung frontend hoàn chỉnh cho dự án workshop: xác thực người dùng, layout điều hướng, các trang quản lý chính (Dashboard, Content, Persona).
* Hoàn thành ContentEditor — màn hình trung tâm của toàn bộ sản phẩm, nơi người dùng thực sự tạo ra nội dung marketing bằng AI.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành |
| --- | --- | --- | --- |
| 2 | - Xây dựng ProtectedRoute: kiểm tra trạng thái đăng nhập, tự khôi phục phiên khi reload trang. <br> - Xây dựng cấu trúc routing đầy đủ (route công khai/route bảo vệ), các trang placeholder ban đầu. <br> - Xây dựng Login.tsx và Register.tsx: validate form, xử lý lỗi từ API, tự động đăng nhập sau khi đăng ký. <br> - Xây dựng AppLayout: layout 2 cột, sidebar điều hướng, hiển thị thông tin người dùng/tổ chức. | 22/06/2026 | 22/06/2026 |
| 3 | - Xây dựng các UI component dùng chung (Spinner, Badge hiển thị trạng thái). <br> - Hoàn thiện Dashboard: widget mức sử dụng token, danh sách nội dung gần đây, lối tắt thao tác nhanh. <br> - Hoàn thiện trang danh sách nội dung: lọc theo loại/trạng thái/chiến dịch ngay từ phía server. | 23/06/2026 | 23/06/2026 |
| 4 | - Xây dựng các UI component tái sử dụng (Button, Input, Select). <br> - Xây dựng form quản lý Brand Persona (tone, giọng điệu, đối tượng mục tiêu, từ khóa) dùng chung cho tạo mới và chỉnh sửa. <br> - Hoàn thiện trang danh sách Persona: đặt mặc định, sửa, xóa. <br> - Fix bug: form chỉnh sửa Persona không tự điền lại dữ liệu mảng (từ khóa, ví dụ mẫu) khi vào chế độ sửa. | 24/06/2026 | 24/06/2026 |
| 5 | - **[Milestone]** Xây dựng ContentEditor — màn hình chính của sản phẩm: chọn loại nội dung, chọn Persona, nhập brief, sinh nội dung bằng AI. <br> - Kết nối cơ chế polling để theo dõi tiến trình xử lý AI theo thời gian thực (không cần WebSocket). <br> - Xây dựng các thao tác hậu kỳ: Viết lại / Mở rộng / Rút gọn nội dung, và lịch sử phiên bản (khôi phục lại bản cũ). <br> - Fix bug: race condition khi polling (kết quả job cũ ghi đè job mới), dữ liệu brief/loại nội dung bị mất khi tạo lại nội dung. | 25/06/2026 | 25/06/2026 |

### Kết quả đạt được tuần 10:
* Hoàn thành toàn bộ luồng xác thực và điều hướng người dùng:
  * Phiên đăng nhập được khôi phục tự động khi tải lại trang, tránh văng người dùng ra ngoài không cần thiết.
* Hoàn thiện các trang quản lý chính với dữ liệu thật từ backend (không còn placeholder):
  * Dashboard tổng hợp đúng dữ liệu usage/quota đã xây ở tuần 9.
  * Trang quản lý Persona cho phép cấu hình đầy đủ "giọng thương hiệu" — tính năng cốt lõi khác biệt của sản phẩm.
* Hoàn thành ContentEditor — cột mốc quan trọng nhất của toàn bộ workshop:
  * Người dùng thực hiện được trọn vẹn hành trình: chọn Persona → nhập ý tưởng → AI sinh nội dung → chỉnh sửa hậu kỳ → xem lại lịch sử phiên bản.
  * Xử lý đúng bài toán đồng thời (concurrency) khi polling nhiều job liên tiếp — vá được lỗi race condition trước khi ảnh hưởng đến trải nghiệm demo.
* Rút ra kinh nghiệm quan trọng: cùng một dữ liệu (brief, loại nội dung) cần được đồng bộ nhất quán giữa các lần gọi API PATCH khác nhau — sai sót nhỏ ở tầng dữ liệu có thể làm mất nội dung người dùng đã nhập, cần test kỹ các luồng chỉnh sửa lặp lại.