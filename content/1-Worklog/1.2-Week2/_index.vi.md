---
title: "Worklog Tuần 2"
date: 2024-10-15T00:00:00Z
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---



### Mục tiêu tuần 2:

* Hiểu sâu hơn về kiến trúc mạng trong AWS, bao gồm cách thiết kế và triển khai VPC với các thành phần như subnet công khai và riêng tư, route table, Internet Gateway, NAT Gateway và Security Group; mục tiêu là nắm rõ vai trò từng thành phần trong việc cách ly và điều phối luồng mạng giữa các tài nguyên cloud.
* Nâng cao khả năng quản lý lưu trữ bằng cách thực hành các tính năng nâng cao của S3 (như versioning, lifecycle rule) và thao tác với EBS snapshots; mục tiêu là biết cách bảo vệ dữ liệu, tối ưu chi phí lưu trữ và phục hồi khi cần.
* Làm quen với công cụ giám sát và ghi nhật ký của AWS — triển khai CloudWatch để thu thập metric và tạo alarm cơ bản, đồng thời bật CloudTrail để ghi lại các hoạt động API nhằm phục vụ công tác kiểm tra và phân tích sự cố.
* Nhận biết và trải nghiệm bước đầu với Infrastructure as Code (IaC) thông qua viết một template CloudFormation hoặc cấu hình Terraform đơn giản; mục tiêu là hiểu quy trình tái tạo hạ tầng bằng mã thay vì thao tác thủ công.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | Bắt đầu tuần bằng việc nghiên cứu lý thuyết về VPC và các thành phần liên quan, sau đó thực hành tạo một VPC mới trong AWS Console với tối thiểu một subnet công khai và một subnet riêng tư; đồng thời cấu hình Internet Gateway để cho phép subnet công khai truy cập Internet và tạo route table phù hợp để liên kết các thành phần này.| 15/09/2025   | 16/09/2025      |https://000003.awsstudygroup.com/vi/1-introduce/
| 3   | Tiếp tục bằng việc cấu hình NAT Gateway cho phép các instance trong subnet riêng tư có thể truy cập Internet khi cần (ví dụ cập nhật gói, tải về dependency), kiểm tra và xác nhận luồng lưu lượng bằng cách dùng các lệnh ping/curl từ EC2 và rà soát route table để hiểu cách NAT hoạt động thực tế.| 16/09/2025   | 18/09/2025      | <https://000003.awsstudygroup.com/vi/1-introduce/1.4-natgateway/> |
| 4   | Nghiên cứu S3 nâng cao và áp dụng tính năng versioning cho một bucket thử nghiệm, đồng thời tạo lifecycle rule để tự động chuyển các đối tượng cũ sang lớp lưu trữ rẻ hơn hoặc xóa sau một khoảng thời gian nhất định; song song đó thực hành tạo EBS snapshot cho một volume dùng thử và ghi nhận thời gian phục hồi.| 17/09/2025   | 19/09/2025      | <https://000057.awsstudygroup.com/vi/1-introduce/> |
| 5   | Thiết lập cơ bản cho CloudWatch: lựa chọn metric phù hợp từ EC2, tạo một dashboard đơn giản hiển thị CPU, network và disk I/O, sau đó cấu hình alarm để gửi thông báo khi CPU utilization vượt ngưỡng; đồng thời bật CloudTrail ở cấp tài khoản để ghi lại các API calls và kiểm tra file log để hiểu cấu trúc sự kiện.| 18/09/2025   | 20/09/2025      | <https://000004.awsstudygroup.com/vi/> |
| 6   | Bắt tay vào IaC bằng việc viết một CloudFormation template (hoặc file Terraform nếu ưa thích) đơn giản tạo một EC2 instance kèm Security Group cơ bản và một S3 bucket; thử deploy stack, quan sát quá trình tạo resource, và sau đó xóa stack để luyện thao tác rollback và cleanup an toàn.| 19/09/2025   | 21/09/2025      | <https://000004.awsstudygroup.com/vi/5-amazonec2basic/> |


### Kết quả đạt được tuần 2:

* Đã thiết kế và triển khai thành công một VPC đơn giản, bao gồm cả subnet công khai và riêng tư, kèm theo Internet Gateway và route table điều phối luồng mạng giữa các subnet; việc này giúp hiểu rõ cách tách biệt tài nguyên để tăng cường bảo mật.
* Đã cấu hình và kiểm chứng Security Group cho EC2, xác nhận các rule cho phép SSH và HTTP hoạt động đúng như mong đợi, đồng thời nhận diện các cấu hình mở quá mức cần tránh để giảm bề mặt tấn công.
* Thực hành các tính năng quản lý dữ liệu trong S3 như bật versioning và tạo lifecycle rule để tự động chuyển đổi hoặc xóa đối tượng theo chính sách; qua đó thấy rõ cách tối ưu chi phí lưu trữ và bảo vệ dữ liệu khỏi xóa nhầm.
* Thực hiện tạo EBS snapshot thủ công cho một volume thử nghiệm và tiến hành phục hồi volume từ snapshot để đảm bảo quy trình backup-phục hồi hoạt động trơn tru; ghi nhận thời gian và bước cần thiết để khôi phục.
* Thiết lập CloudWatch dashboard cơ bản và cấu hình alarm cho metric CPU của EC2, đồng thời bật CloudTrail để ghi lại các hoạt động API; việc này giúp có thể theo dõi hiệu suất và audit hành động trong tài khoản.
* Viết và triển khai một CloudFormation template đơn giản, quan sát quy trình deploy và teardown stack, hiểu được lợi ích của IaC trong việc tái tạo hạ tầng và giảm thiểu thao tác thủ công.