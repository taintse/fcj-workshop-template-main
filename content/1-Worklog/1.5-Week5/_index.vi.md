---
title: "Worklog Tuần 5" 
date: 2025-10-13T00:00:00Z
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Hiểu và thực hành phương thức cấp quyền truy cập cho ứng dụng trên AWS
* Nắm vững cách sử dụng Access Key/Secret Access Key và hạn chế của chúng
* Thực hành triển khai và quản lý IAM Role cho EC2
* Làm quen với dịch vụ AWS IAM và các thành phần cơ bản

### Công việc cần triển khai trong tuần:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | --------- | ------------ | --------------- | ------------------ |
| 2 | Tìm hiểu về Access Key & Secret Access Key: cách tạo, quản lý và các rủi ro bảo mật khi sử dụng. Thực hành tạo key pair và cấu hình AWS CLI. | 6/10/2025 | 7/10/2025 | https://000048.awsstudygroup.com/vi/ |
| 3 | Học về IAM Role: tạo role mới cho EC2, cấu hình trust relationship và attach policies phù hợp. Test role bằng cách gán cho EC2 instance. | 7/10/2025 | 8/10/2025 | https://000048.awsstudygroup.com/vi/3-iamroleec2/ |
| 4 | Thực hành IAM cơ bản: tạo users, groups, áp dụng policies theo best practices. Kiểm tra và audit quyền truy cập. | 8/10/2025 | 9/10/2025 | https://000048.awsstudygroup.com/vi/3-iamroleec2/3.2-useiamrole/|
| 5 | So sánh và đánh giá: thử nghiệm các phương thức xác thực khác nhau, ghi nhận ưu/nhược điểm. Tìm hiểu về security best practices. | 9/10/2025 | 12/10/2025 | |
| 6 | Tổng kết: rà soát cấu hình bảo mật, xóa access keys không cần thiết, kiểm tra IAM Credential Report. Ghi chép lại các bước quan trọng. | 10/10/2025 | 12/10/2025 | Ghi chép cá nhân |

### Thành tựu tuần:

* Access Keys & Authentication:
  * Hiểu rõ về cách tạo và quản lý access keys an toàn
  * Thực hành cấu hình AWS CLI với credentials
  * Nắm được các rủi ro và hạn chế khi sử dụng access keys

* IAM Roles:
  * Tạo và cấu hình thành công IAM role cho EC2
  * Hiểu về trust relationship và cách attach policies
  * Kiểm tra được quyền truy cập khi sử dụng role

* IAM Management:
  * Thực hành tạo users, groups theo best practices
  * Áp dụng được các policies phù hợp
  * Biết cách audit và theo dõi quyền truy cập

* Security Best Practices:
  * Đánh giá được ưu/nhược điểm của các phương thức xác thực
  * Áp dụng các security best practices cho IAM
  * Dọn dẹp và quản lý tài nguyên IAM hiệu quả

### Kết luận:

Tuần này đã nắm vững các khái niệm cơ bản về IAM và phương thức xác thực trên AWS. Việc thực hành với access keys và IAM roles giúp hiểu rõ cách quản lý quyền truy cập an toàn và hiệu quả cho ứng dụng cloud.