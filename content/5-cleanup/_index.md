---
title : "Clean up"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5. </b> "
---
1. Empty S3 bucket
- Open [AWS S3 console](https://s3.console.aws.amazon.com/s3/buckets?region=ap-southeast-1)
- Select **fcj-book-store**
- Click **Empty**
- Enter **permanently delete**
- Click **Empty**
- Do the same for bucket starting with **aws-sam-cli-managed-default-**
2. Delete CloudFormation stacks
- Execute the below command to delete the AWS SAM application
```
sam delete --stack-name fcj-book-store
sam delete --stack-name aws-sam-cli-managed-default
```
3. Delete CloudFront distribution
- Open [Amazon CloudFront console](https://us-east-1.console.aws.amazon.com/cloudfront/v3/home?region=ap-southeast-1#/distributions)
- Select the currently displayed distribution
- Click **Disable**
- Click **Disable** again
- Wait for distribution to be disabled
- Select distribution again and click **Delete**
- Click **Delete** again
4. Delete SSL certificate
- Open [AWS Certificate Manager console](https://us-east-1.console.aws.amazon.com/acm/home?region=us-east-1#/certificates/list)
- Select created certificate
- Click **Delete**
- Click **Delete** again
5. Delete Hosted zone
- Open [Amazon Route 53 console](https://us-east-1.console.aws.amazon.com/route53/v2/hostedzones#)
- Click created hosted zone
- Select records whose type is different from NS and SOA
- Click **Delete records**
- Click **Delete**
- Click **Delete zone**
- Enter **delete**
- Click **Delete**