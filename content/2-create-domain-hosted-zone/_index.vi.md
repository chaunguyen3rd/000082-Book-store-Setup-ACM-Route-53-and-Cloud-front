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

1. Open [Amazon Route 53](https://us-east-1.console.aws.amazon.com/route53/home?region=us-east-1#).

2. If you don't own a domain, follow this step to register a new domain. At **Route 53** console page.
    - Click **Registered domains** on the left menu.
      ![CreateDomain](/images/temp/1/8.png?width=90pc)
    - At **Registered domains** page, click **Register domains** button.
      ![CreateDomain](/images/temp/1/9.png?width=90pc)
    - At **Register domains** page.
      - Enter the domain name you want to create at **Search for domain** box, ex: **fcjbookshop.com**.
      - Click **Search** button.
      - Click **Selected**.
      - Click **Proceed to checkout**.
        ![CreateDomain](/images/temp/1/10.png?width=90pc)
    - At **Step 1: Pricing** page.
      - Uncheck to off Auto-renew the domain after it expires.
      - Click **Next** button.
        ![CreateDomain](/images/temp/1/11.png?width=90pc)
    - At **Step 2: Contact information** page.
      - Enter your information.
      - Scroll down and click **Next** button.
        ![CreateDomain](/images/temp/1/12.png?width=90pc)
    - At **Step 3: Review and submit** page.
      - Scroll down and check **I have read and agree ...**.
      - Click **Submit** button.
        ![CreateDomain](/images/temp/1/13.png?width=90pc)

3. If you already own your domain, you could follow this step. At **Route 53** console page.
{{% notice note %}}
[Making Route 53 the DNS service for a domain that's in use](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/migrate-dns-domain-in-use.html)
{{% /notice %}}
    - Click **Hosted zones** on the left menu.
    ![CreateDomain](/images/temp/1/4.png?width=90pc)
    - At **Hosted zones** page.
      - Click **Create hosted zone** button.
        ![CreateDomain](/images/temp/1/5.png?width=90pc)
      - At **Create hosted zone** page.
        - Enter your domain name at **Domain name**.
        - Click **Create hosted zone** button.
          ![CreateDomain](/images/temp/1/6.png?width=90pc)
      - Check your new hosted zone.
        ![CreateDomain](/images/temp/1/7.png?width=90pc)

We are done creating a hosted name, next step we will request a SSL certificate with AWS Certificate Manager.
