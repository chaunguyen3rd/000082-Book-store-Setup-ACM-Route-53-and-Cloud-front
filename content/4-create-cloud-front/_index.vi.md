---
title : "Tạo CloudFront distribution"
date :  2025-02-11 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
1. Mở [Amazon CloudFront console](https://us-east-1.console.aws.amazon.com/cloudfront/v3/home?region=us-east-1#/distributions).

2. Tại trang **CloudFront**.
    - Click nút **Create a CloudFront distribution**.
      ![CreateDistribution](/images/temp/1/21.png?width=90pc)
    - Tại trang **Create distribution**.
      - Chọn **fcj-book-shop-by-myself.s3.us-east-1.amazonaws.com** tại **Origin domain**.
      - Nhập `fcj-book-shop-by-myself.s3.us-east-1.amazonaws.com` tại **Name**.
      - Chọn **Legacy access identities**.
      - Click **Create new OAI**.
        ![CreateDistribution](/images/temp/1/22.png?width=90pc)
    - Tại popup **Create new OAI**.
      - Nhập **fcj-book-shop-by-myself.s3.us-east-1.amazonaws.com** tại **Name**.
      - Click nút **Create**.
        ![CreateDistribution](/images/temp/1/23.png?width=90pc)
    - Tại trang **Create distribution**.
      - Cuộn xuống, chọn **Yes, update the bucket policy** tại **Bucket policy**.
      - Chọn **Redirect HTTP to HTTPS** tại **Viewer protocol policy**.
      ![CreateDistribution](/images/temp/1/24.png?width=90pc)
      - Cuộn xuống, chọn **Do not enable security protections** tại **Web Application Firewall (WAF)**.
      ![CreateDistribution](/images/temp/1/27.png?width=90pc)
      - Cuộn xuống, click nút **Add item** tại **Alternate domain name (CNAME)**.
      - Nhập **<www.chaunguyen.site>**.
      - Nhập **chaunguyen.site**.
      - Chọn chứng chỉ ***.chaunguyen.site (...)** mà bạn đã tạo trước đó.
        ![CreateDistribution](/images/temp/1/25.png?width=90pc)
      - Cuộn xuống cuối trang, nhập **index.html** tại **Default root object**.
      - Click nút **Create distribution**.
        ![CreateDistribution](/images/temp/1/26.png?width=90pc)

3. Mở [Amazon Route 53](https://us-east-1.console.aws.amazon.com/route53/home?region=us-east-1#).
    - Click **Hosted zones** ở menu bên trái.
    - Chọn **chaunguyen.site**.
      ![CreateDistribution](/images/temp/1/28.png?width=90pc)
    - Tại trang **chaunguyen.site**.
      - Click nút **Create record**.
      ![CreateDistribution](/images/temp/1/29.png?width=90pc)
    - Tại trang **Create record**.
      - Nhập **www** tại **Record name**.
      - Chọn **A - Routes traffic to an IPv4 ...** tại **Record type**.
      - Bật **Alias**.
      - Chọn **Alias to CloudFront distribution**.
      - Chọn CloudFront distribution mà bạn đã tạo ở bước trước.
      - Click nút **Create records**.
      ![CreateDistribution](/images/temp/1/30.png?width=90pc)

4. Nhập các đường dẫn sau vào tab mới trong trình duyệt web của bạn: `http://DOMAIN`, `http://www.DOMAIN`, thay thế tất cả **DOMAIN** bằng tên miền của bạn. Tất cả các đường dẫn này sẽ được chuyển hướng sang đường dẫn mới, thay thế http bằng https
![CreateDistribution](/images/temp/1/31.png?width=90pc)
