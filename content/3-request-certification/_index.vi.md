---
title : "Yêu cầu chứng chỉ SSL"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---
1. Open [AWS Certificate Manager console](https://us-east-1.console.aws.amazon.com/acm/home?region=us-east-1#/welcome).
{{% notice note %}}
The required region to generate the certificate is N.Virginia (us-east-1)
{{% /notice %}}

2. At **AWS Certificate Manager (ACM)** page.
    - Click **Request certificate** on the left menu
      ![RequestCertificate](/images/temp/1/14.png?width=90pc)
    - At **Request certificate** page.
      - Choose **Request a public certificate**.
      - Click **Next** button.
        ![RequestCertificate](/images/temp/1/15.png?width=90pc)
    - At **Request public certificate** page.
      - Enter ***.chaunguyen.site**.
      - Click **Add another name to this certificate**.
      - Enter **chaunguyen.site**.
        ![RequestCertificate](/images/temp/1/16.png?width=90pc)
      - Leave as default, scroll down and click **Request** button.
        ![RequestCertificate](/images/temp/1/17.png?width=90pc)
    - At **35bcec96-7527-4c2e-99ff-3f961c58a81d** certificate page that just created.
      - Click **Create records in Route 53**.
        ![RequestCertificate](/images/temp/1/18.png?width=90pc)
    - At **Create DNS records in Amazon Route 53** page.
      - Check both ***.chaunguyen.site** and **chaunguyen.site**.
      - Click **Create records**.
        ![RequestCertificate](/images/temp/1/19.png?width=90pc)
    - Back to **35bcec96-7527-4c2e-99ff-3f961c58a81d** certificate page.
      - Wait for moment to AWS confirm your domain, after successful confirmation change the status to **Success**.
        ![RequestCertificate](/images/temp/1/20.png?width=90pc)

We have successfully requested an SSL certificate. This certificate will be used by CloudFront in the next step.
