---
title: "Blog 3 "
date: 2025-03-26T00:00:00Z
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# Từ máy ảo đến Kubernetes rồi đến không máy chủ: Dacadoo đã tiết kiệm 78% chi phí đám mây và hoạt động tự động như thế nào

**Tác giả:** Andreas Gehrig, Kevin Nash, Philippe Wanner  
**Ngày đăng:** 26 tháng 3 năm 2025  
**Danh mục:** Amazon API Gateway, Amazon DynamoDB, Amazon Route 53, Amazon Simple Storage Service (S3), Architecture, AWS Cloud Financial Management, AWS Lambda, AWS WAF, Migration, Serverless, Thought Leadership

---

## Giới thiệu

**Dacadoo** là một công ty công nghệ toàn cầu có trụ sở tại **Thụy Sĩ**, chuyên phát triển các giải pháp cho:
- **Tương tác sức khỏe kỹ thuật số**
- **Định lượng rủi ro sức khỏe**

Các sản phẩm của họ bao gồm một **nền tảng SaaS** dựa trên:
- **Khoa học hành vi**
- **Trí tuệ nhân tạo (AI)**
- **Trò chơi điện tử**

Để giúp người dùng cuối **cải thiện kết quả sức khỏe** của họ.

### Hành trình hiện đại hóa

Công ty đã bắt đầu hành trình **hiện đại hóa API** để:
- Định lượng dữ liệu về sức khỏe và lối sống
- Cung cấp công cụ đánh giá rủi ro
- Tính toán xác suất **tử vong và bệnh tật** dựa trên **dữ liệu nghiên cứu khoa học**

Để chuyển đổi dịch vụ API dựa trên **máy ảo** thành giải pháp **tính toán điểm sức khỏe và rủi ro dự phòng toàn cầu**, dacadoo đã chọn **Amazon Web Services (AWS)**.

### Kết quả đạt được

Kết quả là:
- ✅ **Giảm 78% chi phí**
- ✅ **Thời gian bảo trì cơ sở hạ tầng chỉ < 1 giờ/năm**
- ✅ **Cung cấp nhiều cơ sở hạ tầng AWS** mà không cần mở rộng nhóm SRE
- ✅ **Mức độ tự động hóa cao** và **tư duy nhanh nhẹn**

---

## Bối cảnh: Ba giai đoạn tiến hóa

Kiến trúc giải pháp trải qua **ba giai đoạn**:

### **Giai đoạn 1: Ủ với máy ảo**
- Máy ảo đơn tại cơ sở với khả năng phục hồi sau thảm họa (DR) tại Thụy Sĩ

### **Giai đoạn 2: Toàn cầu và có khả năng mở rộng**
- Nhiều cụm Kubernetes toàn cầu

### **Giai đoạn 3: Hoạt động xuất sắc**
- Hoàn toàn không cần máy chủ và dự phòng địa lý trên AWS

---

## Giai đoạn 1: Ủ với máy ảo

### Kiến trúc ban đầu

Sau nhiều năm **nghiên cứu và phát triển khoa học**, dịch vụ này đã được ra mắt, chạy trên:
- **Một máy ảo tại chỗ duy nhất**
- Sử dụng **công nghệ siêu giám sát** để cung cấp **khả năng phục hồi sau thảm họa (DR)**

Ứng dụng phục vụ các yêu cầu:
- **API requests**
- **Cơ sở dữ liệu NoSQL**

**Tất cả chạy trên cùng một máy chủ.**

### Những thách thức

| Vấn đề | Chi tiết |
|--------|---------|
| **Khả năng sẵn sàng** | Không có HA, cần phục hồi thủ công |
| **Triển khai phần mềm** | Thực hiện thủ công bằng SSH |
| **Bảo trì hệ điều hành** | Thực hiện thủ công |
| **Mức độ tự động hóa** | Rất thấp |
| **Sao lưu dữ liệu** | Bằng ảnh chụp nhanh máy ảo |
| **Giám sát** | Thủ công, không có tự động hóa |
| **Kiểm tra** | Chỉ trên máy trạm của nhà phát triển |

### Hạn chế chính

- API chỉ khả dụng ở **Thụy Sĩ**
- Bảo trì được thực hiện **thủ công**
- Triển khai phần mềm được xử lý **thủ công**
- Không có **khả năng mở rộng toàn cầu**
- **Sự cố quản lý nhân lực**

---

## Giai đoạn 2: Toàn cầu và có khả năng mở rộng với Kubernetes

### Quyết định chiến lược

Dacadoo đã đưa ra **quyết định chiến lược** đầu tư mạnh vào:
- **Kubernetes** để quản lý **khối lượng công việc container hóa**
- **Quản lý toàn cầu** ở quy mô lớn

### Triển khai toàn cầu

Do **lượng khách hàng phân bổ theo địa lý** và **yêu cầu độ trễ thấp**:

**Ba cụm Kubernetes được triển khai:**
- Mỗi cụm ở **một châu lục**
- Cơ sở dữ liệu NoSQL được **lưu trữ gần với khối lượng công việc**
- Giảm **độ trễ dịch vụ** và **giảm thiểu nỗ lực di chuyển**

### Tối ưu hóa vận hành

**Cơ sở dữ liệu NoSQL:**
- Tích hợp dưới dạng **dịch vụ SaaS**
- **Giảm thiểu bảo trì hoạt động**

**Giám sát:**
- Tập trung bằng **Datadog**

**Cấp phát cơ sở hạ tầng:**
- Độc quyền với **Terraform**
- Bao gồm: Cụm Kubernetes, cơ sở dữ liệu NoSQL, tích hợp GitLab & Datadog

**CI/CD:**
- Sử dụng **GitLab CI/CD**
- Triển khai **nhiều môi trường và cụm**
- Hệ thống siêu quy mô toàn cầu

### Bảng so sánh: VM vs Kubernetes

| Tiêu chí | Máy ảo | Kubernetes |
|----------|--------|-----------|
| **Khả năng mở rộng** | Thấp | Cao |
| **Tính khả dụng** | Nỗ lực tốt nhất | 99.95% |
| **Chi phí cơ sở hạ tầng** | Thấp | Cao |
| **Nỗ lực bảo trì** | Cao | Trung bình |

### Những thách thức

**Chi phí tăng cao:**
- Ba cụm Kubernetes khu vực
- Ba môi trường
- Tổng cộng: **27 nút cụm**

**Chi phí bổ sung:**
- Quản lý **phiên bản SaaS cơ sở dữ liệu NoSQL** cho mỗi cụm

**Độ phức tạp:**
- Quy trình **CI/CD đa cụm đa môi trường**
- Nỗ lực vận hành **đáng kể** để duy trì cơ sở hạ tầng
- Cần **cập nhật liên tục** các thành phần Kubernetes

---

## Giai đoạn 3: Hoạt động xuất sắc với không máy chủ

### Tại sao chuyển sang không máy chủ?

Kiến trúc dựa trên **Kubernetes đáp ứng được các yêu cầu**, nhưng:
- Một số **tính năng trong danh sách tồn đọc** của API cần **phù hợp hơn**
- Kiến trúc cần **phù hợp với công nghệ mới nhất**
- Cần **tối ưu hóa các phương pháp hay nhất**

Đây là **thời điểm thích hợp** để:
- Có cái nhìn **toàn diện** về cơ sở hạ tầng và kiến trúc phần mềm
- **Tái cấu trúc** giải pháp theo công nghệ AWS **mới nhất**

### Yêu cầu giải pháp

Các yêu cầu đối với **việc tái cấu trúc**:

✅ **Giữ nguyên chức năng của API**

✅ **Hạn chế xử lý dữ liệu** trong phạm vi khu vực được lựa chọn (tuân thủ luật bảo vệ dữ liệu địa phương)

✅ **Tránh chu kỳ vá lỗi hàng tuần** - chỉ sử dụng dịch vụ không máy chủ được quản lý

✅ **Giảm chi phí** - chọn dịch vụ có mô hình thanh toán **theo mức sử dụng**

✅ **Ủy quyền xác thực** cho dịch vụ chuyên dụng

✅ **Sử dụng khuôn khổ web** đã thiết lập với hệ sinh thái rộng lớn

### Tái cấu trúc ứng dụng

**Dịch vụ API bao gồm:**
1. **Cổng thông tin dành cho nhà phát triển** (Developer Portal)
2. **API tính toán điểm số sức khỏe và rủi ro**

**Cơ sở dữ liệu chỉ yêu cầu:**
- Khóa API
- Tham số thuật toán
- Hạn ngạch (Quota)
- Thống kê sử dụng

### Cơ sở dữ liệu phân tán

**Dữ liệu sức khỏe:**
- Được **xử lý theo vùng** bởi **lớp tính toán**
- **KHÔNG được lưu trữ** (chỉ xử lý tạm thời)
- Mở ra cơ hội cho **cơ sở dữ liệu phân tán**

**Amazon DynamoDB Global Tables:**
- Lựa chọn **hoàn hảo** cho giải pháp này
- **Lệnh ghi:** Phân phối đến tất cả Vùng được kết nối
- **Lệnh đọc:** Thực hiện **cục bộ**
- **Độ trễ thấp** - tuân thủ SLA của Dacadoo

### Các thành phần kiến trúc

**Cổng thông tin nhà phát triển:**
- Giao diện người dùng web
- Tài liệu API
- Quản lý khóa API
- **AWS Lambda** - tự động mở rộng, thanh toán theo yêu cầu

**API sức khỏe và rủi ro:**
- Thuật toán triển khai bằng **C** (mô phỏng ngắn hạn)
- Đòi hỏi **tính toán chuyên sâu**
- REST API đóng gói bằng **Python FastAPI**
- **AWS Lambda** - lựa chọn tuyệt vời

---

## Kiến trúc không máy chủ chi tiết

### Luồng yêu cầu

**Các yêu cầu HTTP:**
1. Định tuyến bằng **Amazon API Gateway**
2. Bảo vệ bằng **AWS WAF** (chống yêu cầu độc hại)
3. Chuyển đến **AWS Lambda functions**

**Tài nguyên tĩnh:**
- Cung cấp từ **Amazon S3**
- Thông qua **API Gateway**
- Không cần CloudFront (giảm độ phức tạp)

### Định tuyến DNS toàn cầu

**Amazon Route 53 - Latency-based Routing:**
- **Chuyển hướng truy vấn DNS** đến điểm cuối có **độ trễ thấp nhất**
- Cung cấp **HA theo khu vực** cho người dùng API
- **Không yêu cầu** vị trí xử lý dữ liệu cụ thể
- Người dùng có thể gọi **điểm cuối khu vực cụ thể** (nếu cần tuân thủ pháp lệ)

### Xác thực và ủy quyền

**Ủy quyền API:**
- Dựa trên **tiêu đề HTTP**
- Thực hiện trong **ứng dụng**
- Dữ liệu lưu trữ trong **Amazon DynamoDB**

---

## Infrastructure as Code với Pulumi

### Lựa chọn công cụ

Nhóm SRE **thành thạo Python**, nên chọn **Pulumi**:

**Ưu điểm:**
- ✅ **Cấu trúc kiểm soát luồng** - ngôn ngữ lập trình
- ✅ **Khả năng cấu hình mạnh mẽ**
- ✅ **Hỗ trợ đa đám mây**

### CI/CD Pipeline

**GitLab CI:**
1. **Biên dịch** thư viện thuật toán
2. **Kiểm tra** ứng dụng FastAPI
3. **Đóng gói** mọi thứ

**Triển khai:**
- Chỉ là **cập nhật AWS Lambda**
- Quy trình làm việc **đơn giản và đáng tin cậy**

### Nâng cao kỹ năng

**Chuyển đổi:**
- Từ **cách tiếp cận dựa trên cấu hình**
- Đến **thiết kế cơ sở mã nguồn cơ sở hạ tầng**
- Sử dụng **Python hướng đối tượng**

**Kết quả:**
- SRE phát triển **kỹ năng kỹ thuật phần mềm**
- Đầu tư vào **hiện đại hóa đội ngũ**
- Văn hóa **GitOps tập trung vào năng suất**

---

## Bảng so sánh toàn diện

| Tiêu chí | Máy ảo | Kubernetes | Không máy chủ |
|----------|--------|-----------|--------------|
| **Khả năng mở rộng** | Thấp | Cao | **Rất cao** |
| **Khả dụng** | Nỗ lực tốt nhất | 99.95% | **99.999%*** |
| **Chi phí cơ sở hạ tầng** | Thấp | Cao | **Thấp** |
| **Nỗ lực bảo trì** | Cao | Trung bình | **Rất thấp** |

*Với dự phòng toàn cầu nâng cao khả năng sử dụng lên **99.999%** trong khi vẫn giữ chi phí ở mức **thấp**.

---

## Kết quả cuối cùng

### Chi phí & hiệu suất

✅ **Giảm 78% chi phí**

✅ **Thời gian bảo trì < 1 giờ/năm**

✅ **Khả dụng 99.999%** (toàn cầu)

✅ **Tự động hóa hoàn toàn**

### Lợi ích chiến lược

✅ Cung cấp **nhiều cơ sở hạ tầng AWS** mà **không cần mở rộng nhóm SRE**

✅ **Đơn giản hóa** sự phức tạp của quản lý tài nguyên

✅ **Tăng cường** tính linh hoạt và tự động hóa

✅ **Duy trì** đội ngũ SRE **tinh gọn**

✅ **Giữ chi phí** cơ sở hạ tầng **ở mức thấp**

---

## Kết luận

Việc di chuyển từ **máy ảo** → **Kubernetes** → **AWS Lambda** cho thấy:

**Sự tiến triển của kỹ thuật đám mây** hướng tới:
- 📈 **Hiệu quả**
- 📈 **Khả năng mở rộng được nâng cao**

**Mỗi bước trong hành trình:**
- ⬇️ Giảm thiểu **sự phức tạp của quản lý tài nguyên**
- ⬆️ Tăng cường **tính linh hoạt và tự động hóa**

**Kết quả cho Dacadoo:**
- ✨ Nền tảng **phát triển** mạnh mẽ
- ✨ **Nâng cao kỹ năng** cho các kỹ sư
- ✨ **Duy trì** đội ngũ SRE tinh gọn
- ✨ **Giữ chi phí** ở mức **cạnh tranh**

---

## Hãy bắt đầu

**Hãy bắt đầu** với **giải pháp không máy chủ AWS** của riêng bạn!

---

## Giới thiệu về tác giả

### Andreas Gehrig

**Vị trí:** Kiến trúc sư Điện toán Đám mây thực hành tại Dacadoo, Zurich, Thụy Sĩ

**Nền tảng:** Kỹ thuật phần mềm

**Chuyên môn:** Tận dụng công nghệ AWS để thiết kế và xây dựng các giải pháp đám mây gốc cho ứng dụng và phân tích

### Kevin Nash

**Vị trí:** Kiến trúc sư Giải pháp Cấp cao tại Amazon Web Services (AWS), Thụy Sĩ

**Nền tảng:** Hệ thống phân tán

**Chuyên môn:** Xây dựng giải pháp cho khách hàng, hỗ trợ khách hàng di chuyển giải pháp lên Đám mây

### Philippe Wanner

**Vị trí:** Kiến trúc sư Giải pháp Chuyên gia Cấp cao tại AWS

**Chuyên môn:** Phổ biến phương pháp tối ưu về di chuyển và hiện đại hóa

**Trọng tâm hiện tại:** Lĩnh vực đa ngành xoay quanh:
- Hệ thống phân tán
- Kiến trúc không máy chủ
- Chuyển đổi doanh nghiệp

