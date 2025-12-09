---
title: "Các bài blogs đã dịch"
date: 2024-10-15T00:00:00Z
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Các bài blog AWS đã được dịch và tổng hợp dưới đây:

### [Blog 1 ](3.1-Blog1/)

**Tác giả:** Sébastien Stormacq  
**Ngày đăng:** 26 tháng 3 năm 2025  
**Danh mục:** Announcements, AWS Amplify, AWS WAF, Featured, Front-End Web & Mobile, Launch, News, Security, Identity, & Compliance

**Tóm tắt:** 
Bài viết giới thiệu tính năng tích hợp AWS WAF (Web Application Firewall) với AWS Amplify Hosting, giúp bạn trực tiếp gắn tường lửa ứng dụng web vào ứng dụng Amplify chỉ bằng một cú nhấp chuột trong console Amplify hoặc sử dụng Infrastructure as Code (IaC). 

Trước đây, để triển khai một hệ thống bảo mật mạnh mẽ cho các ứng dụng Amplify, bạn cần sử dụng Amazon CloudFront với AWS WAF, đòi hỏi thêm các bước cấu hình phức tạp. Giờ đây, tính năng mới này đơn giản hóa quá trình này.

**Các tính năng chính:**
- Bảo vệ chống lại các lỗ hổng phổ biến (SQL injection, XSS)
- Hạn chế quyền truy cập theo quốc gia (Geo-blocking)
- Hạn chế quyền truy cập IP
- Bảo vệ DDoS bằng giới hạn tốc độ yêu cầu
- Hạn chế quyền truy cập tên miền amplifyapp.com

**Bốn loại bảo vệ:**
1. Bảo vệ được Amplify khuyến nghị – chống lại các lỗ hổng phổ biến
2. Hạn chế quyền truy cập amplifyapp.com – chặn truy cập tên miền mặc định
3. Bảo vệ IP – cho phép/chặn theo phạm vi IP
4. Bảo vệ theo quốc gia – hạn chế quyền truy cập theo quốc gia

**Giá cả:**
- Tuân theo mô hình định giá AWS WAF tiêu chuẩn
- Cộng thêm $15/tháng khi gắn tường lửa ứng dụng web
- Tính theo giờ

**Tính khả dụng:**
- Có sẵn ở tất cả các khu vực AWS mà Amplify Hosting hoạt động
- Web ACL có thể được đính kèm vào nhiều ứng dụng Amplify, nhưng phải nằm trong cùng khu vực

Bài viết cung cấp ví dụ thực tế về cách kiểm tra AWS WAF bằng cách mô phỏng tấn công (gửi yêu cầu với User-Agent rỗng), giám sát thông qua AWS WAF console, và phân tích nhật ký để tinh chỉnh các quy tắc bảo mật.

### [Blog 2 - Từ người mới bắt đầu sử dụng đám mây đến nhà phát triển trò chơi đoạt giải thưởng](3.2-Blog2/)

**Tác giả:** Carlie Marvel  
**Ngày đăng:** 01 tháng 4 năm 2025  
**Danh mục:** Amazon Bedrock, Amazon CloudFront, Amazon DynamoDB, Amazon Q Developer, Amazon Route 53, Amazon Simple Storage Service (S3), AWS Lambda, Đào tạo và chứng nhận AWS

**Tóm tắt:**
Câu chuyện về hành trình của JC Boissy từ một chuyên gia quản lý dự án CNTT không có kinh nghiệm thực tế về đám mây đến trở thành một nhà phát triển game đoạt giải thưởng nhờ vào AWS Cloud Institute. Trò chơi CloudJack-21 kết hợp cơ chế blackjack với giáo dục về các dịch vụ AWS, sử dụng các công cụ AI như Amazon Q Developer để tối ưu hóa quá trình phát triển.

**Điểm nổi bật:**
- Chương trình AWS Cloud Institute cung cấp 12 khóa học, 150+ phòng thí nghiệm thực hành
- Hành trình từ khái niệm đến kiến trúc không máy chủ nâng cao
- Sử dụng AWS Lambda, DynamoDB, S3, CloudFront, Route 53
- Tận dụng AI tools: Amazon Q Developer và PartyRock
- Cộng đồng học tập hỗ trợ 24/7 qua Slack
- Chứng chỉ đạt được: Cloud Practitioner, AI Practitioner, Solutions Architect Associate

### [Blog 3 - Từ máy ảo đến Kubernetes rồi đến không máy chủ: Dacadoo đã tiết kiệm 78% chi phí đám mây](3.3-Blog3/)

**Tác giả:** Andreas Gehrig, Kevin Nash, Philippe Wanner  
**Ngày đăng:** 26 tháng 3 năm 2025  
**Danh mục:** Amazon API Gateway, Amazon DynamoDB, Amazon Route 53, Amazon Simple Storage Service (S3), Architecture, AWS Cloud Financial Management, AWS Lambda, AWS WAF, Migration, Serverless, Thought Leadership

**Tóm tắt:**
Hành trình hiện đại hóa của công ty Dacadoo từ kiến trúc máy ảo đơn lẻ sang Kubernetes toàn cầu, và cuối cùng sang kiến trúc không máy chủ hoàn toàn. Qua ba giai đoạn này, Dacadoo đã giảm 78% chi phí cơ sở hạ tầng, giảm thời gian bảo trì xuống dưới 1 giờ/năm, và đạt được khả dụng 99.999% với dự phòng địa lý.

**Điểm nổi bật:**
- **Giai đoạn 1 - Máy ảo:** Khả dụng tốt nhất, bảo trì thủ công, chi phí thấp
- **Giai đoạn 2 - Kubernetes:** Ba cụm toàn cầu, 99.95% availability, chi phí cao, bảo trì trung bình
- **Giai đoạn 3 - Serverless:** AWS Lambda, 99.999% availability, chi phí 78% thấp hơn, tự động hóa cao
- Sử dụng DynamoDB Global Tables, API Gateway, Route 53 latency-based routing
- Infrastructure as Code với Pulumi (Python-based)
- CI/CD tự động hóa với GitLab

