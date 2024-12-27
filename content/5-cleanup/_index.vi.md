---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5. </b> "
---
1. Làm rỗng S3 bucket
- Mở bảng điều khiển của [AWS S3](https://s3.console.aws.amazon.com/s3/buckets?region=ap-southeast-1)
- Chọn **fcj-book-store**
- Ấn **Empty**
- Nhập **permanently delete**
- Ấn **Empty**
- Làm tương tự với bucket bắt đầu bằng **aws-sam-cli-managed-default-**
2. Xoá stack của CloudFormation
- Chạy câu lệnh dưới đây để xoá ứng dụng AWS SAM
```
sam delete --stack-name fcj-book-store
sam delete --stack-name aws-sam-cli-managed-default
```
3. Xoá CloudFront distribution
- Mở bảng điều khiển của [Amazon CloudFront](https://us-east-1.console.aws.amazon.com/cloudfront/v3/home?region=ap-southeast-1#/distributions)
- Chọn distribution đang hiện thị
- Ấn **Disable**
- Ấn **Disable** lần nữa
- Chờ distribution được vô hiệu hoá
- Chọn lại distribution và ấn **Delete**
- Ấn **Delete**
4. Xoá SSL certificate
- Mở bảng điều khiển của [AWS Certificate Manager](https://us-east-1.console.aws.amazon.com/acm/home?region=us-east-1#/certificates/list)
- Chọn certificate đã tạo
- Ấn **Delete**
- Ấn **Delete** lần nữa
5. Xoá Hosted zone
- Mở bảng điều khiển của [Amazon Route 53](https://us-east-1.console.aws.amazon.com/route53/v2/hostedzones#)
- Ấn vào hosted zone đã tạo
- Chọn các record có kiểu khác kiểu NS và SOA
- Ấn **Delete records**
- Ấn **Delete**
- Ấn **Delete zone**
- Nhập **delete**
- Ấn **Delete**