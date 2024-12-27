---
title : "Preparation"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
Before we get to the main content of this workshop, we need to reset the web application.
1. Download the below source code

{{%attachments title="Source code" pattern=".*\.(zip)$"/%}}

2. Run the below commands
    ```
    sam build
    sam deploy --guided
    ```

3. Enter the following content:

    - Stack Name []: `fcj-book-shop`
    - AWS Region []: `us-east-1`
    - Confirm changes before deploy [Y/n]: y
    - Allow SAM CLI IAM role creation [Y/n]: y
    - Disable rollback [y/N]: n
    - BooksList may not have authorization defined, Is this okay? [y/N]: y
    - BookCreate may not have authorization defined, Is this okay? [y/N]: y
    - BookDelete may not have authorization defined, Is this okay? [y/N]: y
    - Save arguments to configuration file [Y/n]: y

4. Open [AWS APIs Gateway console](https://ap-southeast-1.console.aws.amazon.com/apigateway/main/apis?region=us-east-1). Then click **API Gateway REST API to Lambda**
    ![CreateUserPool](/images/1/1.png?width=90pc)

6. Click **Stage** on the left menu
    - Click **staging**
    - Record the **InvokeURL**
    ![CreateUserPool](/images/1/2.png?width=90pc)

7. Run the below command to download the source code of **FCJ-Serverless-Workshop** to your device
    ```
    git clone https://github.com/AWS-First-Cloud-Journey/FCJ-Serverless-Workshop.git
    ```
    - Open **config.js** file, replace value of **APP_API_URL** with **InvokeURL**

8. Run the below commands to build project
    ```
    cd FCJ-Serverless-Workshop
    yarn build
    ```
9. We have finished building the front-end. Next, run the below command to upload **build** folder to S3 bucket
    ```
    aws s3 cp build s3://fcj-book-shop --recursive
    ```
So we have rebuilt the web application.
