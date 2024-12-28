---
title : "Yêu cầu chứng chỉ SSL"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---
1. Mở [AWS Certificate Manager console](https://us-east-1.console.aws.amazon.com/acm/home?region=us-east-1#/welcome).
{{% notice note %}}
Khu vực yêu cầu để tạo chứng chỉ là N.Virginia (us-east-1)
{{% /notice %}}

2. Tại trang **AWS Certificate Manager (ACM)**.
    - Nhấp vào **Request certificate** ở menu bên trái
      ![RequestCertificate](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/14.png?width=90pc)
    - Tại trang **Request certificate**.
      - Chọn **Request a public certificate**.
      - Nhấn nút **Next**.
        ![RequestCertificate](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/15.png?width=90pc)
    - Tại trang **Request public certificate**.
      - Nhập ***.chaunguyen.site**.
      - Nhấp vào **Add another name to this certificate**.
      - Nhập **chaunguyen.site**.
        ![RequestCertificate](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/16.png?width=90pc)
      - Giữ nguyên cấu hình mặc định, cuộn xuống và nhấn nút **Request**.
        ![RequestCertificate](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/17.png?width=90pc)
    - Tại trang chứng chỉ **35bcec96-7527-4c2e-99ff-3f961c58a81d** vừa tạo.
      - Nhấn **Create records in Route 53**.
        ![RequestCertificate](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/18.png?width=90pc)
    - Tại trang **Create DNS records in Amazon Route 53**.
      - Chọn cả ***.chaunguyen.site** và **chaunguyen.site**.
      - Nhấn **Create records**.
        ![RequestCertificate](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/19.png?width=90pc)
    - Quay lại trang chứng chỉ **35bcec96-7527-4c2e-99ff-3f961c58a81d**.
      - Đợi một lát để AWS xác nhận tên miền của bạn, sau khi xác nhận thành công trạng thái sẽ chuyển thành **Success**.
        ![RequestCertificate](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/20.png?width=90pc)

Chúng ta đã yêu cầu chứng chỉ SSL thành công. Chứng chỉ này sẽ được sử dụng bởi CloudFront trong bước tiếp theo.
