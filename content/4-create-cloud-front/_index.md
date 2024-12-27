---
title : "Create CloudFront distribution"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
1. Open [Amazon CloudFront console](https://us-east-1.console.aws.amazon.com/cloudfront/v3/home?region=ap-southeast-1#/distributions). Then click **Create distribution**
![CreateDistribution](/images/1/17.png?width=90pc)

3. Select the origin domain is **fcj-book-shop** bucket
![CreateDistribution](/images/1/18.png?width=90pc)

4. Select **Legacy access identities** to just allow access to the S3 bucket from CloudFront 
    - Click **Create new OAI**
![CreateDistribution](/images/1/19.png?width=90pc)

    - Click **Create**
![CreateDistribution](/images/1/20.png?width=90pc)

    - Select OAI you just created
    - Select **Yes, update the bucket policy**
![CreateDistribution](/images/1/21.png?width=90pc)

5. Scroll down, in **Default cache behavior** section, select **Redirect HTTP to HTTPS** for **Viewer protocol policy**
![CreateDistribution](/images/1/22.png?width=90pc)

6. Scroll down, in **Settings** section, click **Add item**
    - Enter CNAME: `www.fcjbookshop.click` and `fcjbookshop.click`
    - Select the SSL certificate you created in previous step
![CreateDistribution](/images/1/23.png?width=90pc)

7. Scroll down to bottom, enter **index.html** for **Default root object** pattern
    - Click **Create distribution**
![CreateDistribution](/images/1/24.png?width=90pc)

8. Go back to the Route 53 console 
    - Click **Create record**
![CreateRecord](/images/1/25.png?width=90pc)

9. Enter `www` for **Record name**
    - Turn on **Alias**
    - Select **Alias to CloudFront distribution**
    - Click **Create records**
![CreateRecord](/images/1/26.png?width=90pc)

11. The record have created
![CreateRecord](/images/1/26.1.png?width=90pc)

13. Enter the following links in a new tab in your web browser: `http://DOMAIN`, `http://www.DOMAIN`, replace all **DOMAIN** with your domain name. All those links redirect to the new path, replace http with https
![CreateRecord](/images/1/27.png?width=90pc)
