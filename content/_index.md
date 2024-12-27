---
title : "Serverless - Setting up SSL for your serverless app"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Serverless - Setting up SSL for your serverless app

#### Overview

In this workshop in the serverless series, we will set up website application to be more sercure in transit by using an SSL certificate. An SSL Certificate allows traffic between a user and a website application hosted on an S3 bucket to be encrypted in transit (in-flight encryption).

The architecture of the web application will look like this:
![SeverlessExample](/images/serverless-diagram.png?featherlight=false&width=50pc)

- AWS Certificate Manager: manage SSL certificates
- Amazon Route 53: provide custom domain
- Amazon CloudFront: allows us to use SSL certificate to serve web with HTTPS

#### AWS Certificate Manager
AWS Certificate Manager (ACM) handles the complexity of creating, storing, and renewing public and private SSL/TLS X.509 certificates and keys that protect your AWS websites and applications. You can provide certificates for your integrated AWS services either by issuing them directly with ACM or by importing third-party certificates into the ACM management system

#### Amazon Route 53
Amazon Route 53 is website service for Domain Name System (DNS) in the cloud. This service is highly available and scalable, disigned for developers and businessees, a reliable and cost-effective way of routing for end users as well as Internet applications by switching domains, such as www.example.com to the IP address (192.0.2.1)

Some feature of Amazon Route 53:
- Efficiently connect user requests to infrastructure running in AWS – like Amazon EC2 instances, Elastic Load Balancing load balancers, or Amazon S3 repositories
- Routing users to infrastructure outside of AWS
- Configure DNS health checks to route traffic to qualified endpoints
- Independently monitor the health of applications and endpoints

One component that we'll be using for Route 53 is the Hosted zone - which is a container of records that defines how to route traffic to a domain of its subdomains.

#### Amazon CloudFront
Amazon CloudFront is a web service that speeds up distribution of your static and dynamic web content, such as .html, .css, .js, and image files, to your users. CloudFront delivers your content through a worldwide network of data centers called edge locations. When a user requests content that you're serving with CloudFront, the request is routed to the edge location that provides the lowest latency (time delay), so that content is delivered with the best possible performance.

A simple approach for storing and delivering static content is to use an Amazon S3 bucket. Using S3 together with CloudFront has a number of advantages, including the option to use origin access control to easily restrict access to your S3 content.

#### Content

 1. [Preparation](1-preparation/)
 2. [Create Domain and Hosted zone](2-create-domain-hosted-zone/)
 3. [Request SSL certificate](3-request-certificate/)
 4. [Create CloudFront distribution](4-create-cloud-front/)
 5. [Cleanup](5-cleanup)
