---
title: "Worklog Tuần 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:
* Bắt đầu triển khai dự án workshop — **AI Content Generator Platform**: SaaS tạo nội dung marketing bằng AI theo Brand Persona (giọng thương hiệu riêng của từng doanh nghiệp).
* Hoàn thành toàn bộ backend core: authentication, brand persona, content generation bất đồng bộ qua SQS, export đa định dạng, usage/quota.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành |
| --- | --- | --- | --- |
| 2 | - Scaffold monorepo (backend/frontend/infrastructure), Docker Compose (PostgreSQL+Redis+LocalStack). <br> - Thiết kế Prisma schema 11 bảng multi-tenant, config layer (database/redis/aws/logger). <br> - Xây dựng Auth flow đầy đủ (register/login/refresh/logout/me + JWT rotation), Brand Persona CRUD + Redis cache, Content CRUD + async operations đẩy vào SQS. <br> - Viết worker.ts (SQS consumer → AI provider → lưu ContentVersion + UsageLog). | 15/06/2026 | 15/06/2026 |
| 3 | - Campaign CRUD hoàn chỉnh (multi-tenant filter, soft delete). <br> - Test end-to-end toàn luồng: register → tạo persona → tạo content → generate → poll job. <br> - Fix nhiều bug: chuẩn hóa kiểu dữ liệu persona, tham số sai khi enqueue SQS, cấu hình client AI provider. | 16/06/2026 | 16/06/2026 |
| 4 | - Xây dựng Export Service: sinh file PDF/DOCX/HTML từ nội dung, upload S3 và trả về presigned URL. <br> - Thêm chế độ Mock cho AI Provider để phát triển không phụ thuộc chi phí AI thật. <br> - Fix lỗi cấu hình S3 Client khi dùng với môi trường giả lập local. | 17/06/2026 | 17/06/2026 |
| 5 | - Xây dựng tính năng theo dõi mức sử dụng (usage) theo tháng, theo model AI. <br> - Thực hiện Quota Enforcement: chặn sinh nội dung khi vượt hạn mức, logic dùng chung giữa API và Worker. <br> - Xây dựng trang quản lý tổ chức (Org Settings): xem/cập nhật hạn mức, phân quyền theo vai trò (OWNER/ADMIN). | 18/06/2026 | 18/06/2026 |

### Kết quả đạt được tuần 9:
* Hoàn thành toàn bộ backend core của dự án workshop trong 5 ngày đầu:
  * Kiến trúc multi-tenant chuẩn: mọi bảng có `organizationId`, mọi query đều filter theo tổ chức — tránh rò rỉ dữ liệu giữa các khách hàng khác nhau.
  * Luồng xử lý bất đồng bộ hoàn chỉnh: API nhận request → đẩy job vào SQS → trả response ngay → Worker xử lý AI ở nền → cập nhật kết quả — áp dụng đúng kiến trúc Serverless/Queue đã học ở tuần 7.
  * Cơ chế Quota dùng chung giữa API và Worker — tránh trùng logic, đảm bảo enforce nhất quán ở cả hai nơi.
* Xây dựng thành công tính năng Export đa định dạng (PDF/DOCX/HTML) với cơ chế tải file an toàn qua presigned URL, không public trực tiếp bucket lưu trữ.
* Thiết lập chế độ Mock cho AI Provider — cho phép phát triển và test song song mà không tốn chi phí gọi AI thật liên tục.
* Áp dụng thành thạo trong thực tế nhiều kỹ năng đã học ở các tuần trước: multi-tenant filtering (tư duy least-privilege), async job pattern (SQS/Worker), quản lý dữ liệu quan hệ với Prisma/PostgreSQL.