---
title : "Chuẩn bị"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
Trước khi thực hiện nội dung chính của workshop này, chúng ta cần thiết lập lại ứng dụng web bằng AWS SAM.
1. Tải source code dưới đây

{{%attachments title="Source code" pattern=".*\.(zip)$"/%}}

2. Chạy các câu lệnh dưới đây
    ```
    sam build
    sam deploy --guided
    ```

3. Nhập nội dung như sau:
    - Stack Name []: `fcj-book-shop`
    - AWS Region []: `us-east-1`
    - Confirm changes before deploy [Y/n]: y
    - Allow SAM CLI IAM role creation [Y/n]: y
    - Disable rollback [y/N]: n
    - BooksList may not have authorization defined, Is this okay? [y/N]: y
    - BookCreate may not have authorization defined, Is this okay? [y/N]: y
    - BookDelete may not have authorization defined, Is this okay? [y/N]: y
    Save arguments to configuration file [Y/n]: y

4. Mở bảng điều khiển của [AWS APIs Gateway](https://ap-southeast-1.console.aws.amazon.com/apigateway/main/apis?region=us-east-1). Sau đó, ấn chọn **API Gateway REST API to Lambda**
![CreateUserPool](/images/1/1.png?width=90pc)

6. Ấn chọn **Stage** ở menu phía bên trái
    - Ấn chọn **staging**
    - Ghi lại **InvokeURL**
![CreateUserPool](/images/1/2.png?width=90pc)

7. Thực hiện câu lệnh dưới đây để tải code **FCJ-Serverless-Workshop** về máy của bạn
    ```
    git clone https://github.com/AWS-First-Cloud-Journey/FCJ-Serverless-Workshop.git
    ```
    - Mở tệp **config.js**, thay giá trị của **APP_API_URL** bằng **InvokeURL**

8. Thực hiện các câu lệnh dưới đây để build project
    ```
    cd FCJ-Serverless-Workshop
    yarn build
    ```
9. Chúng ta đã build xong front-end. Tiếp theo thực hiện câu lệnh sau để tải thư mục **build** lên S3 bucket
    ```
    aws s3 cp build s3://fcj-book-shop --recursive
    ```
Vậy là chúng ta đã tạo lại xong ứng dụng web.
