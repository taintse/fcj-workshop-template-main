---
title: "Worklog Tuần 4"
date: 2025-10-06T00:00:00Z
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Học và áp dụng khái niệm cốt lõi của IAM: users, groups, roles, policies và best practices cho least privilege.
* Cấu hình bảo mật tài khoản: bật MFA, đặt chính sách mật khẩu và rà soát access key.
* Thực hành vai trò dựa trên role và kiểm tra role assumption đơn giản (tuỳ chọn) để hiểu trust và permission.
* Kiểm tra và ghi nhận các phát hiện để hardening sau này.

### Công việc cần triển khai trong tuần
| Thứ | Công việc  | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | ----------------- | ------------ | --------------- | ------------------ |
| 2 | Ôn lại kiến thức IAM, tạo một nhóm developers và tạo 1–2 user gắn vào nhóm. Áp dụng các managed policy tối thiểu cần thiết (tránh AdministratorAccess). Ghi lại tên user và policy đã gán. | 29/09/2025 | 30/09/2025 | https://000002.awsstudygroup.com/vi/ |
| 3 | Tạo một custom policy và gán cho nhóm hoặc role. Kiểm thử bằng cách đăng nhập user test hoặc dùng AWS CLI với credential của user đó. Lưu JSON policy và kết quả test. | 30/09/2025 | 01/10/2025 |  |
| 4 | Bật MFA cho các user đã tạo; đặt chính sách mật khẩu cho account (độ dài tối thiểu, độ phức tạp). Xoay vòng hoặc xóa các access key không dùng; ghi lại các bước. | 01/10/2025 | 02/10/2025 | |
| 5 | Tạo một IAM role cho EC2 hoặc dịch vụ khác với trust policy phù hợp và gán quyền cần thiết (least-privilege). Khởi chạy EC2 test hoặc mô phỏng để xác nhận role hoạt động. (Tuỳ chọn) Thiết lập role cross-account để thử chuyển role nếu có thể. | 02/10/2025 | 03/10/2025 | https://000002.awsstudygroup.com/vi/2-create-admin-user-and-group/ |
| 6 | Kiểm toán và dọn dẹp: chạy IAM Access Analyzer hoặc kiểm tra Access Advisor, phát hiện policy quá rộng và thu hẹp hoặc xóa. Lưu các file JSON policy và chụp màn hình. Tổng hợp vấn đề và biện pháp khắc phục. | 03/10/2025 | 04/10/2025 | https://000002.awsstudygroup.com/vi/5-cleanup/ |

### Thành tựu tuần

* Cấu trúc IAM:
  * Đã tạo nhóm developers và user test với quyền có phạm vi hẹp, tránh dùng quyền admin rộng.
  * Viết và áp dụng custom policy giới hạn truy cập S3 cho bucket cụ thể và đã xác thực hoạt động qua CLI/Console.

* Bảo mật tài khoản:
  * Bật MFA cho user test và thiết lập chính sách mật khẩu (độ dài, độ phức tạp).
  * Phát hiện và xoay/xóa access key không dùng để giảm rủi ro.

* Roles và ủy quyền:
  * Tạo role dịch vụ với trust policy phù hợp và gán quyền theo nguyên tắc least-privilege; xác nhận role hoạt động khi dùng từ EC2 hoặc khi assume role.
  * (Tuỳ chọn) Thiết lập thử nghiệm cross-account role để hiểu cơ chế trust và role switching.

* Kiểm toán & dọn dẹp:
  * Chạy IAM Access Analyzer / Access Advisor để phát hiện policy quá rộng; đã thu hẹp hoặc loại bỏ policy rủi ro.
  * Lưu trữ tất cả JSON policy, lệnh đã chạy và ảnh chụp màn hình cho báo cáo tuần.

### Kết luận:

Tuần này củng cố thực hành quản trị truy cập an toàn: áp dụng least privilege, bắt buộc MFA và chính sách mật khẩu, sử dụng role cho dịch vụ và kiểm toán permissions. Các bước đã làm giảm rủi ro và tạo quy trình lặp lại cho quản trị IAM.
