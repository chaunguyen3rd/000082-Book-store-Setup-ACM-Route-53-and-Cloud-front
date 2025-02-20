---
title : "Dọn dẹp tài nguyên"
date :  2025-02-11 
weight : 5
chapter : false
pre : " <b> 5. </b> "
---
1. Xóa S3 bucket.
    - Mở [AWS S3 console](https://s3.console.aws.amazon.com/s3/buckets?region=ap-southeast-1)
    - Chọn **fcj-book-shop-by-myself**.
    - Nhấn **Empty**.
    - Nhập **permanently delete**.
    - Nhấn **Empty**.
    - Làm tương tự với bucket bắt đầu bằng **aws-sam-cli-managed-default-**.

2. Xóa CloudFormation stacks.
    - Thực thi lệnh dưới đây để xóa ứng dụng AWS SAM.

      ```bash
      sam delete --stack-name fcj-book-store
      sam delete --stack-name aws-sam-cli-managed-default
      ```

    - Nếu bạn gặp vấn đề khi xóa bằng lệnh, mở [AWS Cloudformation console](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/getting-started). Sau đó, xóa tất cả các stack liên quan đến workshop này.

3. Xóa CloudFront distribution
    - Mở [Amazon CloudFront console](https://us-east-1.console.aws.amazon.com/cloudfront/v3/home?region=us-east-1#/distributions).
    - Chọn distribution đang hiển thị.
    - Nhấn **Disable**.
    - Nhấn **Disable** lần nữa.
    - Đợi cho đến khi distribution bị vô hiệu hóa.
    - Chọn lại distribution và nhấn **Delete**.
    - Nhấn **Delete** lần nữa.

4. Xóa chứng chỉ SSL.
    - Mở [AWS Certificate Manager console](https://us-east-1.console.aws.amazon.com/acm/home?region=us-east-1#/certificates/list)
    - Chọn chứng chỉ đã tạo.
    - Nhấn **Delete**.
    - Nhập **delete**.
    - Nhấn **Delete**.

5. Xóa Hosted zone
    - Mở [Amazon Route 53 console](https://us-east-1.console.aws.amazon.com/route53/v2/hostedzones#).
    - Nhấn vào hosted zone đã tạo.
    - Chọn các bản ghi có type khác NS và SOA.
    - Nhấn **Delete records**.
    - Nhấn **Delete**.
    - Nhấn **Delete zone**.
    - Nhập **delete**.
    - Nhấn **Delete**.
