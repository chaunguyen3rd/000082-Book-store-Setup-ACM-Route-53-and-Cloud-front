---
title : "Yêu cầu chứng chỉ SSL"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---
1. Mở bảng điiều khiển của [AWS Certificate Manager](https://ap-southeast-1.console.aws.amazon.com/acm/home?region=ap-southeast-1#/welcome)
{{% notice note %}}
Vùng để tạo certificate bắt buộc là N.Virginia (us-east-1)
{{% /notice %}}

2. Ấn **Request a certificate**
![DeployFunction](/images/1/13.png?width=90pc)

3. Ấn **Next**
![DeployFunction](/images/1/14.png?width=90pc)

4. Nhập tên miền: `*.fcjbookshop.click`
    - Ấn **Ađ another name to this certificate**
    - Nhập tên miền khác: `fcjbookshop.click`
    - Ấn nút **Request**
![DeployFunction](/images/1/14.1.png?width=90pc)

5. Ấn chọn vào certificate bạn vừa tạo
    - Đợi một lát để khởi tạo CNAME cho miền, sau đó ấn **Create records in 53**
![DeployFunction](/images/1/15.png?width=90pc)

6. Ấn **Create records**
![DeployFunction](/images/1/16.png?width=90pc)
7. Đợi một lát để AWS xác nhận miền của bạn, sau khi xác nhận thành công chuyển trạng thái sang **Success**
![DeployFunction](/images/1/17.1.png?width=90pc)
Chúng ta đã yêu cầu một SSL certificate thành công. Certificate này sẽ được CloudFront sử dụng ở bước tiếp theo