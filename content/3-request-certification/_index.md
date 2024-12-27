---
title : "Request SSL certificate"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---
1. Open [AWS Certificate Manager console](https://ap-southeast-1.console.aws.amazon.com/acm/home?region=ap-southeast-1#/welcome)
{{% notice note %}}
The required region to generate the certificate is N.Virginia (us-east-1)
{{% /notice %}}

2. Click **Request a certificate**
![DeployFunction](/images/1/13.png?width=90pc)

3. Click **Next**
![DeployFunction](/images/1/14.png?width=90pc)

4. Enter the domain name: `*.fcjbookshop.click`
    - Click **Add another name to this certificate**
    - Enter another domain name: `fcjbookshop.click`
    - Click **Request** button
![DeployFunction](/images/1/14.1.png?width=90pc)

5. Click to certificate you just created
    - Wait for moment to to initialize the CNAME for the domain, then click **Create records in 53**
![DeployFunction](/images/1/15.png?width=90pc)

6. Click **Create records**
![DeployFunction](/images/1/16.png?width=90pc)

7. Wait for moment to AWS confirm your domain, after successful confirmation change the status to **Success**
![DeployFunction](/images/1/17.1.png?width=90pc)
We have successfully requested an SSL certificate. This certificate will be used by CloudFront in the next step.