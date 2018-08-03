---
layout: post
title: AWS 101 & LAB - CloudFront - Draft
---

### Notes
#### What is a CDN?

A content delivery network (CDN) is a system of distributed servers (network) that deliver webpages and other web content to a user based on the geographic locations of the user, the origin of the webpage, and a content deliver servers.
It is WebService that speeds up the distribution of your static and dynamic web content (image, js, html). 

If the webserver is located in US and users use them in Australia, they must be routed to many different networks and it can cause latency and worse performance that for users located in Mexico.

**Exam-tip** - cloud front is focused on content delivery (more efficient reads and downloads). Whereas transfer acceleration is all about enabling faster upload to S3.

Instead of each user accessing directly between the geographical location and US. Instead we introduce the concept called Edge locations. Edge locations is simply collections of servers which are geographically disparates data centers. This Edge location are used for cloud front to keep a cache of copies of your object. Users can access the content from edge location which is much closer than US. First request downloads file and than any user can use data from cache. 

You can clean your cache yourself in order to ensure that users have latest object version - you will be charged for that.

#### CloudFront - Key terminology 

- **Edge Location** - this is the location where content is cached and can also be written. Separate to an AWS Region/AZ.

- **Origin**  - this is the origin of all the files that the CDN will distribute. Origins can be an S3 Bucket, an EC2 Instance an Elastic Load Balancer or Route 53.

- **Distribution** - this is the name given the CDN, which consists of a collection of Edge Locations.
Web Distribution - typically used for Websites (HTTP/HTTPS). 
RTMP - Used for Media Streaming (Real time messaging protocol). 

**Can be used to optimize performance for users accessing a website backed by S3**

#### CloudFront And S3 transfer Acceleration

Amazon S3 transfer acceleration enables fast , easy and secure transfers of files over long distances between your end users and S3 bucket. 

Transfer Acceleration takes advantage of Amazon CloudFront's location, data is routed to Amazon S3 over optimized network path. 

**Exam-tip**

- Edge location are not just READ only - you can WRITE to them  too. (i.e. PUT and object on to them)
- CloudFront Edge Locations are utilized by S3 transfer Acceleration to reduce latency for S3 uploads
- Objects are cached for the life of the TLL(Time to Live)
- You can clear cached objects, but you will be charged.

#### CloudFront - LAB - Creating CDN - Distribution in AWS terminology 

1. Origin - S3 bucket (Australia)
2. Upload 4mb image to see difference
...
3. restricted bucket access in Origin Setup - if yes users do not have the access to the bucket and can only use edge locations

**Exam tip** - Restrict viewer Access (Signed URLs or Signed cookies) -  selling content on website

Invalidation is removing object from the cache before TLL will be active again(default 24h) 

------------
*Notes based mainly on Cloud Guru Course - [AWS Certified Developer](https://acloud.guru/learn/aws-certified-developer-associate-june-2018) and [AWS Whitepapers](https://aws.amazon.com/whitepapers/)*