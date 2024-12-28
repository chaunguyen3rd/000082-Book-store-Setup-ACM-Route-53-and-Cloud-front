---
title : "Serverless - Thiết lập trang web SSL S3 Static"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Serverless - Thiết lập trang web SSL S3 Static

#### Tổng quan

Trong bài này của series, chúng ta sẽ thiết lập để ứng dụng web bảo mật hơn khi transit bằng cách sử dụng SSL Certificate. SSL Certificate cho phép lưu lượng truy cập giữa người dùng và ứng dụng web host trên S3 bucket được mã hoá khi transit (in-flight encryption).

Kiến trúc của ứng dụng web sẽ như sau:
![SeverlessExample](/images/serverless-diagram.png?featherlight=false&width=50pc)

- AWS Certificate Manager: quản lý SSL certificate
- Amazon Route 53: cung cấp domain tuỳ chỉnh
- Amazon CloudFront: cho phép chúng ta sử dụng SSL certificate để phục vụ web với HTTPS

#### AWS Certificate Manager

AWS Certificate Manager (ACM) xử lý các thao tác tạo và gia hạn phức tạp của các chứng chỉ và khoá SSL/TLS X.509 công khai và riêng tư để bảo vệ các trang web và ứng dụng của chúng ta. Chúng ta có thể cung cấp chứng chỉ cho các dịch vụ AWS tích hợp của mình bằng cách cung cấp chúng trực tiếp với ACM hoặc nhập chứng chỉ của bên thứ ba vào hệ thống quản lý ACM.

#### Amazon Route 53

Amazon Route 53 là một dịch vụ web dành cho Hệ thống tên miền (DNS) trên đám mây. Dịch vụ này có tính sẵn sàng và khả năng mở rộng cao, được thiết kế cho nhà phát triển và doanh nghiệp một phương thức tin cậy và giúp tối ưu hiệu quả về chi phí trong việc định tuyến cho người dùng cuối (end user) cũng như các ứng dụng Internet bằng cách chuyển đổi tên miền, ví dụ như <www.example.com> sang địa chỉ IP dạng số (như 192.0.2.1).

Một số tính năng của Amazon Route 53:

- Kết nối hiệu quả yêu cầu của người dùng với cơ sở hạ tầng đang chạy trong AWS – như các phiên bản Amazon EC2, trình cân bằng tải Elastic Load Balancing hoặc kho lưu trữ Amazon S3
- Định tuyến người dùng đến cơ sở hạ tầng bên ngoài AWS
- Cấu hình kiểm tra tình trạng của DNS nhằm định tuyến lưu lượng đến các điểm cuối đủ tiêu chuẩn
- Theo dõi độc lập tình trạng của ứng dụng và các điểm cuối.

Một thành phần mà chúng ta sẽ dùng của Route 53 là Hosted zone - là một vùng chứa các bản ghi xác định cách định tuyến lưu lượng truy cập đến một miển các miền phụ của nó.

#### Amazon CloudFront

Amazon CloudFront là một dich vụ web giúp tăng tốc độ phân phối nội dung web tĩnh và động của bạn, ví dụ như các tệp .html, .js, .css, hình ảnh cho người dùng. CloudFront cung cấp nội dung trang web của chúng ta thông qua mạng lưới các trung tâm dữ liệu trên toàn thế giới được gọi là edge locations. Khi người dùng yêu cầy nội dung mà chúng ta đang phân phối bằng CloutFront, yêu cầu chuyển đến edge location mà cũng cấp độ trễ thấp nhất (time delay), vì vậy nội dung được phân phối với hiệu suất tốt nhất có thể.

Một cách tiếp cận đơn giản để lưu trữ và cung cấp nội dung tĩnh sử dụng Amazon S3 bucket. Sử dụng S3 cùng với CloudFront là một lựa chọn để kiểm soát truy cập origin dễ dàng hạn chế quyền truy cập vào nội dung của bạn.

#### Nội dung

 1. [Chuẩn bị](1-preparation/)
 2. [Tạo miền và Hosted zone](2-create-domain-hosted-zone/)
 3. [Yêu cầu chứng chỉ SSL](3-request-certification/)
 4. [Tạo CloudFront distribution](4-create-cloud-front/)
 5. [Dọn dẹp tài nguyên](5-cleanup)
