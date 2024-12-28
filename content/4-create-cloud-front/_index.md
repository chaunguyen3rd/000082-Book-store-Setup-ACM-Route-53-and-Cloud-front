---
title : "Create CloudFront distribution"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
1. Open [Amazon CloudFront console](https://us-east-1.console.aws.amazon.com/cloudfront/v3/home?region=us-east-1#/distributions).

2. At **CloudFront** page.
    - Click **Create a CloudFront distribution** button.
      ![CreateDistribution](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/21.png?width=90pc)
    - At **Create distribution** page.
      - Choose **fcj-book-shop-by-myself.s3.us-east-1.amazonaws.com** at **Origin domain**.
      - Enter **fcj-book-shop-by-myself.s3.us-east-1.amazonaws.com** at **Name**.
      - Choose **Legacy access identities**.
      - Click **Create new OAI**.
        ![CreateDistribution](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/22.png?width=90pc)
    - At **Create new OAI** popup.
      - Enter **fcj-book-shop-by-myself.s3.us-east-1.amazonaws.com** at **Name**.
      - Click **Create** button.
        ![CreateDistribution](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/23.png?width=90pc)
    - At **Create distribution** page.
      - Scroll down, choose **Yes, update the bucket policy** at **Bucket policy**.
      - Choose **Redirect HTTP to HTTPS** at **Viewer protocol policy**.
        ![CreateDistribution](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/24.png?width=90pc)
      - Scroll down, choose **Do not enable security protections** at **Web Application Firewall (WAF)**.
        ![CreateDistribution](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/27.png?width=90pc)
      - Scroll down, click **Add item** button at **Alternate domain name (CNAME)**.
      - Enter **<www.chaunguyen.site>**.
      - Enter **chaunguyen.site**.
      - Choose ***.chaunguyen.site (...)** certificate that you created before.
        ![CreateDistribution](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/25.png?width=90pc)
      - Scroll down to the bottom, enter **index.html** at **Default root object**.
      - Click **Create distribution** button.
        ![CreateDistribution](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/26.png?width=90pc)

3. Open [Amazon Route 53](https://us-east-1.console.aws.amazon.com/route53/home?region=us-east-1#).
    - Click **Hosted zones** on the left menu.
    - Choose **chaunguyen.site**.
      ![CreateDistribution](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/28.png?width=90pc)
    - At **chaunguyen.site** page.
      - Click **Create record** button.
        ![CreateDistribution](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/29.png?width=90pc)
    - At **Create record** page.
      - Enter **www** at **Record name**.
      - Choose **A - Routes traffic to an IPv4 ...** at **Record type**.
      - Enable **Alias**.
      - Choose **Alias to CloudFront distribution**.
      - Choose CloudFront distribution you created on the previous step.
      - Click **Create records** button.
        ![CreateDistribution](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/30.png?width=90pc)

4. Enter the following links in a new tab in your web browser: `http://DOMAIN`, `http://www.DOMAIN`, replace all **DOMAIN** with your domain name. All those links redirect to the new path, replace http with https
![CreateDistribution](/images/000082-Book-store-Setup-ACM-Route-53-and-Cloud-front/temp/1/31.png?width=90pc)
