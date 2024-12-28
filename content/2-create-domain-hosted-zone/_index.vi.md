---
title : "Tạo miền và Hosted zone"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2. </b> "
---
Trong bước này, chúng ta sẽ tạo một Domain và Hosted zone với Amazon Route 53.

{{% notice warning %}}
Việc tạo miền sẽ tốn chi phí của bạn.
{{% /notice %}}

1. Mở [Amazon Route 53](https://us-east-1.console.aws.amazon.com/route53/home?region=us-east-1#).

2. Nếu bạn chưa sở hữu một miền, hãy làm theo bước này để đăng ký một miền mới. Tại trang điều khiển **Route 53**.
    - Nhấp vào **Registered domains** trên menu bên trái.
      ![CreateDomain](/images/temp/1/8.png?width=90pc)
    - Tại trang **Registered domains**, nhấp vào nút **Register domains**.
      ![CreateDomain](/images/temp/1/9.png?width=90pc)
    - Tại trang **Register domains**.
      - Nhập tên miền bạn muốn tạo vào ô **Search for domain**, ví dụ: **fcjbookshop.com**.
      - Nhấp vào nút **Search**.
      - Nhấp vào **Selected**.
      - Nhấp vào **Proceed to checkout**.
        ![CreateDomain](/images/temp/1/10.png?width=90pc)
    - Tại trang **Step 1: Pricing**.
      - Bỏ chọn để tắt tự động gia hạn miền sau khi hết hạn.
      - Nhấp vào nút **Next**.
        ![CreateDomain](/images/temp/1/11.png?width=90pc)
    - Tại trang **Step 2: Contact information**.
      - Nhập thông tin của bạn.
      - Cuộn xuống và nhấp vào nút **Next**.
        ![CreateDomain](/images/temp/1/12.png?width=90pc)
    - Tại trang **Step 3: Review and submit**.
      - Cuộn xuống và chọn **I have read and agree ...**.
      - Nhấp vào nút **Submit**.
        ![CreateDomain](/images/temp/1/13.png?width=90pc)

3. Nếu bạn đã sở hữu một miền, bạn có thể làm theo bước này. Tại trang điều khiển **Route 53**.
{{% notice note %}}
[Making Route 53 the DNS service for a domain that's in use](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/migrate-dns-domain-in-use.html)
{{% /notice %}}
    - Nhấp vào **Hosted zones** trên menu bên trái.
      ![CreateDomain](/images/temp/1/4.png?width=90pc)
      - Tại trang **Hosted zones**.
        - Nhấp vào nút **Create hosted zone**.
          ![CreateDomain](/images/temp/1/5.png?width=90pc)
        - Tại trang **Create hosted zone**.
          - Nhập tên miền của bạn vào ô **Domain name**.
          - Nhấp vào nút **Create hosted zone**.
            ![CreateDomain](/images/temp/1/6.png?width=90pc)
        - Kiểm tra hosted zone mới của bạn.
          ![CreateDomain](/images/temp/1/7.png?width=90pc)

Chúng ta đã hoàn tất việc tạo hosted zone, bước tiếp theo chúng ta sẽ yêu cầu chứng chỉ SSL với AWS Certificate Manager.
