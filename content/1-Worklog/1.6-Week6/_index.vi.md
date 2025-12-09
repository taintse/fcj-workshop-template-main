---
title: "Worklog Tuần 6" 
date: 2025-10-20T00:00:00Z
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---
---


### Mục tiêu tuần 6:

* Nâng cao kiến thức về Identity and Access Management (IAM) với các khái niệm advanced
* Tìm hiểu về Amazon DynamoDB - dịch vụ cơ sở dữ liệu NoSQL được quản lý hoàn toàn
* Thực hành tạo, cấu hình và quản lý DynamoDB tables
* Tìm hiểu mô hình pricing và best practices cho DynamoDB

### Công việc cần triển khai trong tuần:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| ---- | --------- | ------------ | --------------- | ------------------ |
| 2 | Ôn tập IAM Advanced: tìm hiểu về policy evaluation logic, resource-based policies, và permission boundaries. Thực hành viết các policy phức tạp hơn. | 20/10/2025 | 21/10/2025 | https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html |
| 3 | Tìm hiểu DynamoDB cơ bản: khái niệm tables, items, attributes, primary keys (partition key & sort key). Tạo một table đơn giản với on-demand billing. | 21/10/2025 | 22/10/2025 | https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html |
| 4 | Thực hành CRUD operations trên DynamoDB: insert, query, update và delete items. Sử dụng AWS Console và AWS CLI. | 22/10/2025 | 23/10/2025 | https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/WorkingWithItems.html |
| 5 | Tìm hiểu về DynamoDB indexes (Global Secondary Indexes - GSI, Local Secondary Indexes - LSI) và cách sử dụng để tối ưu query. Tạo và test một GSI. | 23/10/2025 | 25/10/2025 | https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SecondaryIndexes.html |
| 6 | Tổng kết: rà soát cấu hình IAM policies cho DynamoDB access, kiểm tra CloudWatch metrics, và dọn dẹp tài nguyên không cần thiết. Ghi chép lại các bước quan trọng. | 24/10/2025 | 25/10/2025 | Ghi chép cá nhân |

### Thành tựu tuần:

* IAM Advanced:
  * Hiểu rõ hơn về policy evaluation logic và resource-based policies
  * Viết được các policy phức tạp hơn để điều khiển truy cập DynamoDB

* DynamoDB Fundamentals:
  * Tạo và cấu hình thành công một DynamoDB table
  * Hiểu được các khái niệm key schema và attribute types
  * Thực hành được on-demand billing vs provisioned throughput

* CRUD Operations:
  * Thực hiện thành công các thao tác insert, query, update, delete
  * Sử dụng được AWS Console và AWS CLI để quản lý data
  * Kiểm tra được response time và performance

* Indexing & Optimization:
  * Tạo được Global Secondary Index để tối ưu query patterns
  * Hiểu được khi nào nên sử dụng GSI vs LSI
  * Kiểm tra được query performance metrics

### Kết luận:

Tuần này cung cấp nền tảng vững chắc về DynamoDB - một dịch vụ NoSQL có thể mở rộng cao. Việc kết hợp IAM cho phép kiểm soát truy cập an toàn và hiệu quả.
| 2   | - Làm quen với các thành viên FCJ <br> - Đọc và lưu ý các nội quy, quy định tại đơn vị thực tập                                                                                             | 11/08/2025   | 11/08/2025      |
| 3   | - Tìm hiểu AWS và các loại dịch vụ <br>&emsp; + Compute <br>&emsp; + Storage <br>&emsp; + Networking <br>&emsp; + Database <br>&emsp; + ... <br>                                            | 12/08/2025   | 12/08/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tạo AWS Free Tier account <br> - Tìm hiểu AWS Console & AWS CLI <br> - **Thực hành:** <br>&emsp; + Tạo AWS account <br>&emsp; + Cài AWS CLI & cấu hình <br> &emsp; + Cách sử dụng AWS CLI | 13/08/2025   | 13/08/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu EC2 cơ bản: <br>&emsp; + Instance types <br>&emsp; + AMI <br>&emsp; + EBS <br>&emsp; + ... <br> - Các cách remote SSH vào EC2 <br> - Tìm hiểu Elastic IP   <br>                  | 14/08/2025   | 15/08/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Thực hành:** <br>&emsp; + Tạo EC2 instance <br>&emsp; + Kết nối SSH <br>&emsp; + Gắn EBS volume                                                                                         | 15/08/2025   | 15/08/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 6:
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



