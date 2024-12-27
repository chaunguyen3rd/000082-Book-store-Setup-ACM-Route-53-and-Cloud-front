---
title : "Tạo CloudFront distribution"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

1. Mở bảng điều khiển của [Amazon CloudFront](https://us-east-1.console.aws.amazon.com/cloudfront/v3/home?region=ap-southeast-1#/distributions). Sau đó, Ấn **Create distribution**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-2.png?featherlight=false&width=90pc)

3. Chọn origin domain là S3 bucket **fcj-book-shop**
![CreateDistribution](/images/1/18.png?width=90pc)

4. Chọn **Legacy access identities** để chỉ cho phép truy cập vào S3 bucket từ CloudFront
    - Ấn **Create new OAI**
![CreateDistribution](/images/1/19.png?width=90pc)

    - Ấn **Create**
![CreateDistribution](/images/1/20.png?width=90pc)

    - Chọn OAI bạn vừa tạo
    - Chọn **Yes, update the bucket policy**
![CreateDistribution](/images/1/21.png?width=90pc)
5. Kéo xuống dưới, tại phần **Default cache behavior** chọn **Redirect HTTP to HTTPS** cho **Viewer protocol policy**
![CreateDistribution](/images/1/22.png?width=90pc)

6. Kéo xuống dưới, tại phần **Settings**, ấn **Add item**
    - Nhập CNAME: `www.fcjbookshop.click` và `fcjbookshop.click`
    - Chọn SSL certificate vừa tạo ở phần trước
![CreateDistribution](/images/1/23.png?width=90pc)

7. Kéo xuống cuối trang, nhập **index.html** cho mục **Default root object**
    - Ấn **Create distribution**
![CreateDistribution](/images/1/24.png?width=90pc)

8. Quay trở lại với bảng điều khiển của Route 53
    - Ấn **Create record**
![CreateRecord](/images/1/25.png?width=90pc)

9. Nhập `www` cho **Record name**
    - Bật **Alias**
    - Chọn **Alias to CloudFront distribution**
    - Nhấn **Create records**
![CreateRecord](/images/1/26.png?width=90pc)

11. Record đã được tạo
![CreateRecord](/images/1/26.1.png?width=90pc)

13. Nhập các đường dẫn sau vào một tab mới trong trình duyệt web của bạn: `http://DOMAIN`, `http://www.DOMAIN`, thay toàn bộ **DOMAIN** bằng tên domain của bạn. Tất cả các đường dẫn đó đều chuyển hướng đến đường dẫn mới, thay http bằng https
![CreateRecord](/images/1/27.png?width=90pc)
