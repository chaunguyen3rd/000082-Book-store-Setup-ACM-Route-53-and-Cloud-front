---
title : "Preparation"
date :  2025-02-11 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
Before we get to the main content of this workshop, we need to reset the web application.

1. Download the below source code.

    {{%attachments title="Source code" pattern=".*\.(zip)$"/%}}

2. Run the below commands.
{{% notice note %}}
Ensure you have the AWS CLI and SAM CLI installed on your machine, configure AWS credentials before running the commands.
{{% /notice %}}

    ```bash
    sam build
    sam validate
    sam deploy --guided
    ```

3. Enter the following content. Leave as default.
    - Stack Name []: `fcj-book-store`
    - AWS Region []: `us-east-1`
    - Confirm changes before deploy [Y/n]: y
    - Allow SAM CLI IAM role creation [Y/n]: y
    - Disable rollback [y/N]: n
    - Save arguments to configuration file [Y/n]: y
      ![Preparation](/images/temp/1/1.png?width=90pc)

4. Download the **FCJ-Serverless-Workshop** code to your device.
    - Open a terminal on your computer in the folder where you want to save the source code.
    - Copy the below command.

      ```bash
      git clone https://github.com/AWS-First-Cloud-Journey/FCJ-Serverless-Workshop.git
      cd FCJ-Serverless-Workshop
      ```

    - Then, run the commands below.

      ```bash
      yarn
      yarn build
      ```

5. We have finished building the front-end. Next execute the following command to upload the **build** folder to S3.

    ```bash
    aws s3 cp build s3://fcj-book-shop-by-myself --recursive
    ```

So we have rebuilt the web application.
