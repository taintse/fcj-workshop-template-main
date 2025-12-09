---
title: "Worklog Tuần 3"
date: 2024-10-15T00:00:00Z
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---



### Mục tiêu tuần 3:

* Thực hành việc nhưng đảm bảo nắm vững: một EC2 cơ bản, kiểm tra S3 và rà soát giám sát CloudWatch.
* Nắm được các bước làm chi tiết, có thể hoàn thành nhanh và dễ lặp lại.
* Thực hành cô đọng: 1 EC2, 1 S3, và kiểm tra giám sát CloudWatch.  
* Hoàn tất từng bước rõ ràng, ghi lại lệnh và kết quả.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tạo 1 EC2 (t2.micro), chọn key pair, cấu hình SG chỉ mở SSH cho IP của bạn; ghi Public IP và ID instance. | 22/09/2025   | 22/09/2025      |
| 3   | - Cập nhật OS, cài git/curl; (tuỳ chọn) tạo & mount 1 EBS nhỏ rồi kiểm tra quyền đọc/ghi.| 23/09/2025   | 23/09/2025      |  |
| 4   | - Tạo 1 bucket S3, upload file bằng Console và CLI; thử bật versioning và phục hồi 1 object. | 24/09/2025   | 25/09/2025      | <https://000057.awsstudygroup.com/vi/2-prerequiste/2.1-creates3bucket/> |
| 5   |Thiết lập CloudWatch: xem metric EC2, tạo alarm CPU đơn giản và (tuỳ chọn) SNS notification; kiểm tra log group.| 25/09/2025   | 26/09/2025      | <https://000004.awsstudygroup.com/vi/1-introduce/> |
| 6   | -  Tổng kết: kiểm tra tags, xóa tài nguyên không cần thiết, chụp màn hình bước quan trọng và ghi lỗi/giải pháp.| 26/09/2025   | 26/09/2025      |  |


### Kết quả đạt được tuần 3:

* EC2 và truy cập:
  * Đã khởi tạo EC2 (t2.micro) và xác nhận instance hoạt động bình thường; có thể SSH vào máy qua key pair đã tạo (ghi lại Public IP và ID instance).
  * Đã tạo, format và mount EBS lên instance thành công; kiểm tra quyền đọc/ghi và ghi lại lệnh/đường dẫn mount.

* S3:
  * Tạo bucket thử nghiệm, upload file bằng cả Console và AWS CLI để kiểm tra workflow.
  * Bật versioning cho bucket và thực hành overwrite rồi phục hồi object — restore thành công.

* CloudWatch & Logging:
  * Thiết lập CloudWatch để thu thập metric của EC2 (CPU, Network, Disk) và tạo ít nhất một alarm đơn giản cho CPU.
  * Tạo Log Group và gửi log từ EC2; cấu hình SNS và kiểm tra nhận notification để xác thực flow cảnh báo.

* Quản lý tài nguyên & chi phí:
  * Rà soát các resource đã tạo, gỡ/xóa những tài nguyên không cần thiết (terminate EC2, detach/delete EBS, xóa object tạm trong S3) để tránh phát sinh chi phí.
  * Ghi lại các lệnh, cấu hình, và chụp ảnh màn hình các bước quan trọng để lưu làm báo cáo tuần.

* Kết luận :
  * Hoàn thành các bước thực hành cơ bản: EC2 có thể SSH, EBS (nếu dùng) mount ổn định, S3 upload/restore hoạt động, CloudWatch alarm/log và notification đã được kiểm tra, và tài nguyên dư thừa đã được dọn sạch.
  



