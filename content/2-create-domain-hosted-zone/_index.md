---
title : "Create Domain and Hosted zone"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2. </b> "
---
In this step, we will create a Domain and Hosted zone with Amazon Route 53.

{{% notice warning %}}
Domain creation will cost you.
{{% /notice %}}

1. Open [Amazon Route 53](https://us-east-1.console.aws.amazon.com/route53/home?region=ap-southeast-1#)

2. Select **Registered domains** on the left menu
    - Click **Register Domain**
![CreateDomain](/images/1/3.png?width=90pc)
3. Enter the domain name you want to create, ví dụ: `fcjbookshop`
    - Select the appropriate Top Level Domain
    - Click **Search** to check the domain name is available
    - Click **Selected**
    - Then click **Proceed to checkout**
![CreateDomain](/images/1/4.png?width=90pc)


4. Uncheck to **off** **Auto-renew** the domain after it expires
![CreateDomain](/images/1/5.png?width=90pc)

5. Enter your personal information
![CreateDomain](/images/1/6.png?width=90pc)
7. At **Terms and Conditions** section, check to agree to the terms
    - Click **Submit**
![CreateDomain](/images/1/7.png?width=90pc)

11. Wait for a while, your domain will be ready to use
    - Select **Registered domains** on the left menu
![CreateDomain](/images/1/8.png?width=90pc)
13. Open your email provied above, click to link to verify the domain registration information from **noreply@registrar.amazon.com**
![CreateDomain](/images/1/9.png?width=90pc)
12. After the domain is registered successfully, the hosted zone will be create
    - Select **Hosted zones** on the left menu
![CreateDomain](/images/1/11.png?width=90pc)

14. We are done creating a hosted name, next step we will request a SSL certificate with AWS Certificate Manager
![CreateDomain](/images/1/12.png?width=90pc)
