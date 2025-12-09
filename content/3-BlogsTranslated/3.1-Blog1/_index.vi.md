---
title: "Blog 1 "
date: 2024-10-15T00:00:00Z
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Hỗ trợ Tường lửa cho các trang web được lưu trữ trên AWS Amplify

**Tác giả:** Sébastien Stormacq  
**Ngày đăng:** 26 tháng 3 năm 2025  
**Danh mục:** Announcements, AWS Amplify, AWS WAF, Featured, Front-End Web & Mobile, Launch, News, Security, Identity, & Compliance

---

## Giới thiệu

Hôm nay, chúng tôi thông báo về tính năng tích hợp **AWS WAF (Web Application Firewall)** với **AWS Amplify Hosting**. Chủ sở hữu ứng dụng web luôn nỗ lực bảo vệ ứng dụng của họ khỏi nhiều mối đe dọa khác nhau.

---

## Vấn đề trước đây

Trước đây, nếu muốn triển khai một hệ thống bảo mật mạnh mẽ cho các ứng dụng Amplify Hosted, bạn cần:
- Tạo kiến trúc bằng cách sử dụng **Amazon CloudFront** với khả năng bảo vệ **AWS WAF**
- Yêu cầu thêm các bước cấu hình phức tạp
- Yêu cầu chuyên môn kỹ thuật cao
- Tăng chi phí quản lý đáng kể

---

## Giải pháp mới: Tích hợp AWS WAF với Amplify

Giờ đây, bạn có thể **trực tiếp gắn tường lửa ứng dụng web** vào ứng dụng AWS Amplify của mình thông qua:
- Tích hợp một cú nhấp chuột trong **Amplify console**, hoặc
- Sử dụng **Infrastructure as Code (IaC)**

Tích hợp này cho phép bạn:
- Truy cập **toàn bộ các tính năng của AWS WAF**
- Sử dụng các **quy tắc được quản lý sẵn**
- Tạo **các quy tắc tùy chỉnh** dựa trên nhu cầu ứng dụng cụ thể
- Bảo vệ chống lại các **lỗ hổng web phổ biến**:
  - SQL injection
  - Cross-site scripting (XSS)

---

## Các chiến lược bảo mật mạnh mẽ

### 1. Bảo vệ chống lại DDoS
Bạn có thể tận dụng các **quy tắc dựa trên tốc độ của AWS WAF** để:
- Giới hạn tốc độ yêu cầu từ các địa chỉ IP
- Bảo vệ chống lại các cuộc tấn công từ chối dịch vụ phân tán (DDoS)

### 2. Chặn theo địa lý (Geo-blocking)
- Hạn chế quyền truy cập vào ứng dụng từ các quốc gia cụ thể
- Đặc biệt hữu ích nếu dịch vụ của bạn được thiết kế cho các khu vực địa lý cụ thể

---

## Bốn loại bảo vệ được Amplify cung cấp

### 1. Bảo vệ tường lửa được Amplify khuyến nghị
- Bảo vệ chống lại các **lỗ hổng phổ biến nhất** được tìm thấy trong các ứng dụng web
- **Chặn địa chỉ IP** khỏi các mối đe dọa tiềm ẩn dựa trên thông tin tình báo về mối đe dọa nội bộ của Amazon
- Bảo vệ chống lại các **tác nhân độc hại** phát hiện ra lỗ hổng ứng dụng

### 2. Hạn chế quyền truy cập vào amplifyapp.com
- Hạn chế quyền truy cập vào **tên miền amplifyapp.com** mặc định do Amplify tạo ra
- Hữu ích khi bạn **thêm tên miền tùy chỉnh**
- Ngăn **bot và công cụ tìm kiếm** thu thập thông tin tên miền

### 3. Bảo vệ địa chỉ IP
- Hạn chế lưu lượng truy cập web bằng cách **cho phép hoặc chặn** các yêu cầu từ **phạm vi địa chỉ IP được chỉ định**

### 4. Bảo vệ theo quốc gia
- Hạn chế quyền truy cập theo **quốc gia cụ thể**

---

## Cách thiết lập

Việc thiết lập bảo vệ AWS WAF cho ứng dụng Amplify của bạn **rất đơn giản**:

1. Từ **bảng điều khiển Amplify**, điều hướng đến **cài đặt ứng dụng**
2. Chọn tab **Firewall**
3. Chọn **các quy tắc được xác định trước** mà bạn muốn áp dụng

### Tạo Web Access Control List (ACL)

Các biện pháp bảo vệ được kích hoạt thông qua **Amplify console** sẽ tạo một **Web Access Control List (ACL) cơ bản** trong tài khoản AWS của bạn.

**Cho bộ quy tắc chi tiết hơn:** Sử dụng **trình xây dựng quy tắc** trong bảng điều khiển **AWS WAF**.

### Thời gian hoạt động

Sau **vài phút**, các quy tắc sẽ được **liên kết với ứng dụng** của bạn và **AWS WAF sẽ chặn các yêu cầu đáng ngờ**.

---

## Kiểm tra AWS WAF hoạt động

### Cách mô phỏng tấn công

Bạn có thể **mô phỏng một cuộc tấn công** và **giám sát nó** bằng cách sử dụng chức năng **kiểm tra yêu cầu** của AWS WAF.

**Ví dụ:** Gửi một yêu cầu với **giá trị User-Agent trống** → Điều này sẽ **kích hoạt quy tắc chặn** trong AWS WAF.

### Bước 1: Gửi yêu cầu hợp lệ

Trước tiên, gửi một **yêu cầu hợp lệ** tới ứng dụng của bạn.

**Kết quả:** Máy chủ trả về thông báo **HTTP 200 (OK)**

### Bước 2: Gửi yêu cầu không hợp lệ

Sau đó, gửi một yêu cầu **không có giá trị nào được liên kết với tiêu đề HTTP User-Agent**.

**Kết quả:** Máy chủ trả về thông báo **HTTP 403 (Bị cấm)**

---

## Giám sát và tối ưu hóa

AWS WAF cung cấp **khả năng hiển thị các mẫu yêu cầu**, giúp bạn:
- **Tinh chỉnh cài đặt bảo mật** theo thời gian
- **Phân tích xu hướng lưu lượng truy cập**
- **Cải thiện các quy tắc bảo mật** khi cần

Bạn có thể truy cập **nhật ký** thông qua:
- **Amplify Hosting console**, hoặc
- **Bảng điều khiển AWS WAF**

---

## Tính khả dụng

- **Có sẵn ở tất cả các khu vực AWS** mà Amplify Hosting hoạt động
- Tích hợp này **thuộc tài nguyên toàn cầu AWS WAF** (tương tự như Amazon CloudFront)
- **Lưu ý:** Web ACL có thể được đính kèm vào **nhiều ứng dụng Amplify Hosting**, nhưng chúng phải nằm trong **cùng một khu vực**

---

## Mô hình giá cả

Giá cho tích hợp này tuân theo **mô hình định giá AWS WAF tiêu chuẩn**:

### Chi phí AWS WAF:
Bạn trả tiền cho các tài nguyên AWS WAF bạn sử dụng dựa trên:
- Số lượng **ACL**
- Số lượng **quy tắc**
- Số lượng **yêu cầu web**

### Chi phí bổ sung từ AWS Amplify:
- **$15/tháng** khi bạn gắn tường lửa ứng dụng web vào ứng dụng của mình
- Chi phí này được **tính theo giờ**

---

## Lợi ích chính

Tính năng mới này mang đến các **tính năng bảo mật cấp doanh nghiệp** cho tất cả khách hàng của Amplify Hosting, từ:
- **Nhà phát triển cá nhân**
- Đến **các doanh nghiệp lớn**

**Giờ đây, bạn có thể:**
- **Xây dựng** ứng dụng web
- **Lưu trữ** ứng dụng web  
- **Bảo vệ** ứng dụng web

**Tất cả trong cùng một dịch vụ**, giảm thiểu:
- **Độ phức tạp của kiến trúc**
- **Hợp lý hóa việc quản lý bảo mật**

---

## Kết luận

Tính năng AWS WAF integration với **Amplify Hosting** là một bước tiến quan trọng trong việc đơn giản hóa **bảo mật ứng dụng web**. Với khả năng thiết lập bảo vệ mạnh mẽ chỉ bằng một cú nhấp chuột, các nhà phát triển có thể tập trung vào việc xây dựng ứng dụng của họ mà không phải lo lắng về các phức tạp bảo mật.

---

## Tham khảo và tìm hiểu thêm

- Tài liệu tích hợp **AWS WAF cho Amplify**
- Dùng thử trực tiếp trong **bảng điều khiển Amplify**
- Tài liệu **AWS WAF**

---

## Về tác giả: Sébastien Stormacq

Seb đã viết mã kể từ lần đầu tiên chạm vào Commodore 64 vào giữa những năm tám mươi. Anh ấy truyền cảm hứng cho các nhà phát triển để khai thác giá trị của đám mây AWS, bằng cách sử dụng sự kết hợp bí mật giữa:
- Đam mê
- Nhiệt huyết
- Sự ủng hộ khách hàng
- Sự tò mò
- Tính sáng tạo

**Sở thích của anh ấy:** Kiến trúc phần mềm, công cụ phát triển và điện toán di động.

**Mẹo:** Nếu bạn muốn bán cho anh ấy thứ gì đó, hãy chắc chắn rằng nó có **API**.

**Theo dõi @sebsto trên:** Bluesky, X, Mastodon và các nền tảng khác.

Các data lake có thể giúp các bệnh viện và cơ sở y tế chuyển dữ liệu thành những thông tin chi tiết về doanh nghiệp và duy trì hoạt động kinh doanh liên tục, đồng thời bảo vệ quyền riêng tư của bệnh nhân. **Data lake** là một kho lưu trữ tập trung, được quản lý và bảo mật để lưu trữ tất cả dữ liệu của bạn, cả ở dạng ban đầu và đã xử lý để phân tích. data lake cho phép bạn chia nhỏ các kho chứa dữ liệu và kết hợp các loại phân tích khác nhau để có được thông tin chi tiết và đưa ra các quyết định kinh doanh tốt hơn.

Bài đăng trên blog này là một phần của loạt bài lớn hơn về việc bắt đầu cài đặt data lake dành cho lĩnh vực y tế. Trong bài đăng blog cuối cùng của tôi trong loạt bài, *“Bắt đầu với data lake dành cho lĩnh vực y tế: Đào sâu vào Amazon Cognito”*, tôi tập trung vào các chi tiết cụ thể của việc sử dụng Amazon Cognito và Attribute Based Access Control (ABAC) để xác thực và ủy quyền người dùng trong giải pháp data lake y tế. Trong blog này, tôi trình bày chi tiết cách giải pháp đã phát triển ở cấp độ cơ bản, bao gồm các quyết định thiết kế mà tôi đã đưa ra và các tính năng bổ sung được sử dụng. Bạn có thể truy cập các code samples cho giải pháp tại Git repo này để tham khảo.

---

## Hướng dẫn kiến trúc

Thay đổi chính kể từ lần trình bày cuối cùng của kiến trúc tổng thể là việc tách dịch vụ đơn lẻ thành một tập hợp các dịch vụ nhỏ để cải thiện khả năng bảo trì và tính linh hoạt. Việc tích hợp một lượng lớn dữ liệu y tế khác nhau thường yêu cầu các trình kết nối chuyên biệt cho từng định dạng; bằng cách giữ chúng được đóng gói riêng biệt với microservices, chúng ta có thể thêm, xóa và sửa đổi từng trình kết nối mà không ảnh hưởng đến những kết nối khác. Các microservices được kết nối rời thông qua tin nhắn publish/subscribe tập trung trong cái mà tôi gọi là “pub/sub hub”.

Giải pháp này đại diện cho những gì tôi sẽ coi là một lần lặp nước rút hợp lý khác từ last post của tôi. Phạm vi vẫn được giới hạn trong việc nhập và phân tích cú pháp đơn giản của các **HL7v2 messages** được định dạng theo **Quy tắc mã hóa 7 (ER7)** thông qua giao diện REST.

**Kiến trúc giải pháp bây giờ như sau:**

> *Hình 1. Kiến trúc tổng thể; những ô màu thể hiện những dịch vụ riêng biệt.*

---

Mặc dù thuật ngữ *microservices* có một số sự mơ hồ cố hữu, một số đặc điểm là chung:  
- Chúng nhỏ, tự chủ, kết hợp rời rạc  
- Có thể tái sử dụng, giao tiếp thông qua giao diện được xác định rõ  
- Chuyên biệt để giải quyết một việc  
- Thường được triển khai trong **event-driven architecture**

Khi xác định vị trí tạo ranh giới giữa các microservices, cần cân nhắc:  
- **Nội tại**: công nghệ được sử dụng, hiệu suất, độ tin cậy, khả năng mở rộng  
- **Bên ngoài**: chức năng phụ thuộc, tần suất thay đổi, khả năng tái sử dụng  
- **Con người**: quyền sở hữu nhóm, quản lý *cognitive load*

---

## Lựa chọn công nghệ và phạm vi giao tiếp

| Phạm vi giao tiếp                        | Các công nghệ / mô hình cần xem xét                                                        |
| ---------------------------------------- | ------------------------------------------------------------------------------------------ |
| Trong một microservice                   | Amazon Simple Queue Service (Amazon SQS), AWS Step Functions                               |
| Giữa các microservices trong một dịch vụ | AWS CloudFormation cross-stack references, Amazon Simple Notification Service (Amazon SNS) |
| Giữa các dịch vụ                         | Amazon EventBridge, AWS Cloud Map, Amazon API Gateway                                      |

---

## The pub/sub hub

Việc sử dụng kiến trúc **hub-and-spoke** (hay message broker) hoạt động tốt với một số lượng nhỏ các microservices liên quan chặt chẽ.  
- Mỗi microservice chỉ phụ thuộc vào *hub*  
- Kết nối giữa các microservice chỉ giới hạn ở nội dung của message được xuất  
- Giảm số lượng synchronous calls vì pub/sub là *push* không đồng bộ một chiều

Nhược điểm: cần **phối hợp và giám sát** để tránh microservice xử lý nhầm message.

---

## Core microservice

Cung cấp dữ liệu nền tảng và lớp truyền thông, gồm:  
- **Amazon S3** bucket cho dữ liệu  
- **Amazon DynamoDB** cho danh mục dữ liệu  
- **AWS Lambda** để ghi message vào data lake và danh mục  
- **Amazon SNS** topic làm *hub*  
- **Amazon S3** bucket cho artifacts như mã Lambda

> Chỉ cho phép truy cập ghi gián tiếp vào data lake qua hàm Lambda → đảm bảo nhất quán.

---

## Front door microservice

- Cung cấp API Gateway để tương tác REST bên ngoài  
- Xác thực & ủy quyền dựa trên **OIDC** thông qua **Amazon Cognito**  
- Cơ chế *deduplication* tự quản lý bằng DynamoDB thay vì SNS FIFO vì:
  1. SNS deduplication TTL chỉ 5 phút
  2. SNS FIFO yêu cầu SQS FIFO
  3. Chủ động báo cho sender biết message là bản sao

---

## Staging ER7 microservice

- Lambda “trigger” đăng ký với pub/sub hub, lọc message theo attribute  
- Step Functions Express Workflow để chuyển ER7 → JSON  
- Hai Lambda:
  1. Sửa format ER7 (newline, carriage return)
  2. Parsing logic  
- Kết quả hoặc lỗi được đẩy lại vào pub/sub hub

---

## Tính năng mới trong giải pháp

### 1. AWS CloudFormation cross-stack references
Ví dụ *outputs* trong core microservice:
```yaml
Outputs:
  Bucket:
    Value: !Ref Bucket
    Export:
      Name: !Sub ${AWS::StackName}-Bucket
  ArtifactBucket:
    Value: !Ref ArtifactBucket
    Export:
      Name: !Sub ${AWS::StackName}-ArtifactBucket
  Topic:
    Value: !Ref Topic
    Export:
      Name: !Sub ${AWS::StackName}-Topic
  Catalog:
    Value: !Ref Catalog
    Export:
      Name: !Sub ${AWS::StackName}-Catalog
  CatalogArn:
    Value: !GetAtt Catalog.Arn
    Export:
      Name: !Sub ${AWS::StackName}-CatalogArn

