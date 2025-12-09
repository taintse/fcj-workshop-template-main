---
title: "Worklog Tuần 7"
date: 2024-10-15T00:00:00Z
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---


### Mục tiêu tuần 7:

* Tìm hiểu về Amazon Cognito - dịch vụ quản lý danh tính và xác thực người dùng
* Thực hành tạo User Pool và cấu hình xác thực
* Tìm hiểu về Amazon Location Service - dịch vụ định vị địa lý và bản đồ
* Kết hợp Cognito với ứng dụng và Location Service

### Công việc cần triển khai trong tuần:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | --------- | ------------ | --------------- | ------------------ |
| 2 | Tìm hiểu Cognito cơ bản: User Pools vs Identity Pools, authentication flow, và use cases. Tạo một User Pool đơn giản với password policy. | 26/10/2025 | 27/10/2025 | https://docs.aws.amazon.com/cognito/latest/developerguide/user-pools.html |
| 3 | Cấu hình Cognito User Pool: thêm users, cấu hình email verification, multi-factor authentication (MFA), và password recovery. | 27/10/2025 | 28/10/2025 | https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-lambda-custom-message.html |
| 4 | Tìm hiểu Amazon Location Service: tạo một map resource, sử dụng search place, và tính toán route. Thử nghiệm các API cơ bản. | 28/10/2025 | 29/10/2025 | https://docs.aws.amazon.com/location/latest/developerguide/what-is.html |
| 5 | Kết hợp Cognito với Location Service: cấu hình IAM role để cho phép Cognito user access Location Service resources. Thử nghiệm end-to-end. | 29/10/2025 | 30/10/2025 | https://docs.aws.amazon.com/cognito/latest/developerguide/iam-roles.html |
| 6 | Tổng kết: rà soát cấu hình bảo mật cho cả Cognito và Location Service, kiểm tra CloudWatch logs, và dọn dẹp tài nguyên. Ghi chép lại các bước quan trọng. | 30/10/2025 | 1/11/2025 | Ghi chép cá nhân |

### Thành tựu tuần:

* Cognito User Pool:
  * Tạo thành công một User Pool với cấu hình bảo mật
  * Thêm users và cấu hình xác thực (email verification, MFA)
  * Hiểu được authentication flow và JWT tokens

* Cognito Identity Pool:
  * Tìm hiểu cách cấp quyền tạm thời cho unauthenticated users
  * Cấu hình được IAM roles cho Cognito identities

* Location Service:
  * Tạo map resource và thử nghiệm các API
  * Sử dụng place search và route calculation
  * Hiểu được pricing model

* Integration:
  * Kết hợp thành công Cognito authentication với Location Service resources
  * Cấu hình IAM policies cho phép user access
  * Kiểm tra end-to-end workflow

### Kết luận:

Tuần này giúp nắm được các dịch vụ quản lý danh tính và định vị địa lý của AWS. Kết hợp Cognito với Location Service tạo ra các ứng dụng location-aware với xác thực người dùng an toàn.
| 2   | - Làm quen với các thành viên FCJ <br> - Đọc và lưu ý các nội quy, quy định tại đơn vị thực tập                                                                                             | 11/08/2025   | 11/08/2025      |
| 3   | - Tìm hiểu AWS và các loại dịch vụ <br>&emsp; + Compute <br>&emsp; + Storage <br>&emsp; + Networking <br>&emsp; + Database <br>&emsp; + ... <br>                                            | 12/08/2025   | 12/08/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tạo AWS Free Tier account <br> - Tìm hiểu AWS Console & AWS CLI <br> - **Thực hành:** <br>&emsp; + Tạo AWS account <br>&emsp; + Cài AWS CLI & cấu hình <br> &emsp; + Cách sử dụng AWS CLI | 13/08/2025   | 13/08/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu EC2 cơ bản: <br>&emsp; + Instance types <br>&emsp; + AMI <br>&emsp; + EBS <br>&emsp; + ... <br> - Các cách remote SSH vào EC2 <br> - Tìm hiểu Elastic IP   <br>                  | 14/08/2025   | 15/08/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Thực hành:** <br>&emsp; + Tạo EC2 instance <br>&emsp; + Kết nối SSH <br>&emsp; + Gắn EBS volume                                                                                         | 15/08/2025   | 15/08/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 7:

* Hiểu AWS là gì và nắm được các nhóm dịch vụ cơ bản: 
  * Compute
  * Storage
  * Networking 
  * Database
  * ...

* Đã tạo và cấu hình AWS Free Tier account thành công.

* Làm quen với AWS Management Console và biết cách tìm, truy cập, sử dụng dịch vụ từ giao diện web.

* Cài đặt và cấu hình AWS CLI trên máy tính bao gồm:
  * Access Key
  * Secret Key
  * Region mặc định
  * ...

* Sử dụng AWS CLI để thực hiện các thao tác cơ bản như:

  * Kiểm tra thông tin tài khoản & cấu hình
  * Lấy danh sách region
  * Xem dịch vụ EC2
  * Tạo và quản lý key pair
  * Kiểm tra thông tin dịch vụ đang chạy
  * ...

* Có khả năng kết nối giữa giao diện web và CLI để quản lý tài nguyên AWS song song.
* ...



