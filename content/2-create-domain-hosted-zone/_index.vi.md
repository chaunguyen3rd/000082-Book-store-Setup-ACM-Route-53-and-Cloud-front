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

1. Mở bảng điều khiển của [Amazon Route 53](https://us-east-1.console.aws.amazon.com/route53/home?region=ap-southeast-1#)

2. Chọn **Registered domains** ở phía menu phía bên trái
    - Ấn **Register Domain**
![CreateDomain](/images/1/3.png?width=90pc)

3. Nhập tên miền mà bạn muốn tạo, ví dụ: `fcjbookshop`
    - Lựa chọn Top Level Domain phù hợp.
    - Ấn **Search** để kiểm tra xem tên miền có đang có sẵn không
    - Ấn **Selected**
    - Cuối cùng, nhấn vào **Proceed to checkout**
![CreateDomain](/images/1/4.png?width=90pc)


4. Tắt tính năng **Auto-renew** khi domain hết hạn
![CreateDomain](/images/1/5.png?width=90pc)

5. Nhập các thông tin các nhân của bạn
![CreateDomain](/images/1/6.png?width=90pc)

7. Tại mục **Terms and Conditions**, tích chọn đồng ý với các điều khoản
    - Ấn **Complete Order**
![CreateDomain](/images/1/7.png?width=90pc)

11. Đợi một lúc, miền của bạn sẽ sẵn sàng để sử dụng
    - Ấn chọn **Registered domains** ở menu phía bên trái
![CreateDomain](/images/1/8.png?width=90pc)
13. Mở mail bạn đã đăng kí ở trên, nhấn vào link nhận được từ **noreply@registrar.amazon.com** để xác nhận thông tin đăng kí domain
![CreateDomain](/images/1/9.png?width=90pc)
12. Sau khi miền được đăng ký thành công, chúng ta sẽ tạo một hosted zone
    - Ấn chọn **Hosted zones** ở menu phía bên trái
![CreateDomain](/images/1/11.png?width=90pc)

14. Chúng ta đã hoàn thành tạo một hosted zone, bước tiếp theo chúng ta sẽ yêu cầu một SSL certificate với AWS Certificate Manager
![CreateDomain](/images/1/12.png?width=90pc)
