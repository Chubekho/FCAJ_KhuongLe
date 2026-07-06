---
title: "Worklog Tuần 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:
* Làm quen với containerization — đóng gói ứng dụng bằng Docker để đảm bảo chạy nhất quán giữa các môi trường (local, staging, production).
* Tìm hiểu container orchestration với Amazon ECS/Fargate — vận hành container ở quy mô lớn mà không cần tự quản lý server (serverless container).
* Xây dựng pipeline CI/CD tự động với AWS CodePipeline — nền tảng cho việc tự động hoá deploy ở dự án tốt nghiệp.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu Docker: image, container, Dockerfile, layer caching. <br> - **Thực hành:** Viết Dockerfile cho một ứng dụng đơn giản, build image, chạy thử container local. | 25/05/2026 | 25/05/2026 | [Triển khai Ứng dụng với Docker](https://000015.awsstudygroup.com/vi/) |
| 3 | - Tìm hiểu Amazon ECS: Cluster, Task Definition, Service, Fargate launch type (serverless, không cần quản lý EC2 nền). <br> - **Thực hành:** Đẩy image lên Amazon ECR, deploy container lên ECS chạy trên Fargate. | 26/05/2026 | 26/05/2026 | [Triển khai Ứng dụng lên Amazon ECS](https://000016.awsstudygroup.com/vi/) |
| 4 | - Thực hành lab mở rộng: tách một ứng dụng monolith thành các service nhỏ hơn, containerize và deploy từng phần lên Fargate. | 27/05/2026 | 27/05/2026 | [Monolith to Microservices với Docker và AWS Fargate](https://000067.awsstudygroup.com/vi/) |
| 5 | - Tìm hiểu AWS CodePipeline: Source stage, Build stage (CodeBuild), Deploy stage. <br> - **Thực hành:** Dựng pipeline tự động build Docker image và deploy lên ECS mỗi khi có commit mới trên GitHub. | 28/05/2026 | 28/05/2026 | [Triển khai Ứng dụng với AWS CodePipeline](https://000017.awsstudygroup.com/vi/) |
| 6 | - Thực hành lab CI/CD container hoàn chỉnh: build → push image lên ECR → tự động update ECS Service, không cần thao tác tay ở bất kỳ bước nào. | 29/05/2026 | 29/05/2026 | [CI/CD với CodePipeline](https://000152.awsstudygroup.com/vi/) |

### Kết quả đạt được tuần 6:
* Hiểu và thực hành thành thạo containerization với Docker:
  * Viết được Dockerfile tối ưu (multi-stage build, giảm kích thước image).
  * Phân biệt rõ Image (bản đóng gói tĩnh) và Container (instance đang chạy của image).
* Triển khai thành công ứng dụng container lên Amazon ECS chạy trên Fargate:
  * Hiểu vì sao Fargate phù hợp để tránh phải tự vá lỗi/scale EC2 instance nền cho container.
  * Nắm được luồng: build image → push lên ECR (registry riêng) → ECS pull image để chạy.
* Thực hành tách một ứng dụng từ kiến trúc monolith sang các service nhỏ hơn:
  * Hiểu lợi ích: scale độc lập từng service, dễ maintain, giảm blast radius khi lỗi.
* Xây dựng thành công pipeline CI/CD tự động với CodePipeline:
  * Luồng Source (GitHub) → Build (CodeBuild, build Docker image) → Deploy (cập nhật ECS Service).
  * Hiểu rõ giá trị cốt lõi: mỗi lần push code là tự động có phiên bản mới chạy production, không cần SSH thủ công vào server để deploy.
* Nắm được nền tảng CI/CD container-based — đây chính là mô hình sẽ áp dụng trực tiếp khi build pipeline GitHub Actions cho dự án tốt nghiệp ở các tuần sau (dù công cụ CI khác nhau, tư duy pipeline giống nhau).