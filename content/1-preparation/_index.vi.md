---
title : "Chuẩn bị"
date :  2025-02-11 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
Trước khi thực hiện nội dung chính của workshop này, chúng ta cần thiết lập lại ứng dụng web bằng AWS SAM.

1. Tải xuống mã nguồn dưới đây.

    {{%attachments title="Source code" pattern=".*\.(zip)$"/%}}

2. Chạy các lệnh dưới đây.
{{% notice note %}}
Đảm bảo rằng bạn đã cài đặt AWS CLI và SAM CLI trên máy của mình, cấu hình thông tin xác thực AWS trước khi chạy các lệnh.
{{% /notice %}}

    ```bash
    sam build
    sam validate
    sam deploy --guided
    ```

3. Nhập nội dung sau. Để mặc định.
    - Stack Name []: `fcj-book-store`
    - AWS Region []: `us-east-1`
    - Confirm changes before deploy [Y/n]: y
    - Allow SAM CLI IAM role creation [Y/n]: y
    - Disable rollback [y/N]: n
    - Save arguments to configuration file [Y/n]: y
      ![Preparation](/images/temp/1/1.png?width=90pc)

4. Tải xuống mã nguồn **FCJ-Serverless-Workshop** về thiết bị của bạn.
    - Mở terminal trên máy tính của bạn trong thư mục nơi bạn muốn lưu mã nguồn.
    - Sao chép lệnh dưới đây.

    ```bash
    git clone https://github.com/AWS-First-Cloud-Journey/FCJ-Serverless-Workshop.git
    cd FCJ-Serverless-Workshop
    ```

    - Sau đó chạy các lệnh dưới đây.

      ```bash
      yarn
      yarn build
      ```

5. Chúng ta đã hoàn thành việc xây dựng front-end. Tiếp theo, thực hiện lệnh sau để tải thư mục **build** lên S3.

    ```bash
    aws s3 cp build s3://fcj-book-shop-by-myself --recursive
    ```

Vậy là chúng ta đã xây dựng lại ứng dụng web.
