---
layout: post
title: X-Ray | Amazon Web Services Notes 
---

AWS X-Ray is a service that collects data about requests that your application serves and provides tools you can use to view, filter and gain insights into that data to identify issues and opportunities for optimization. For any traced request to your application, you can see detailed information not only about the request and response, but also calls that your application makes to downstream AWS resources, microservices, databases and HTTP web APIs

### Notes

#### X-Ray Architecture

X-Ray SDK --> X-Ray Daemon --> X-Ray API --> X-Ray Console

#### X-Ray SDK

The X-Ray SDK provides:
* Inceptors to add to your code to trace incoming HTTP requests
* Client handlers to instrument AWS SDK clients that your application uses to call other AWS services
* An HTTP client to use to instrument calls to other internal and external HTTP web services.

#### X-Ray Integration

The X-Ray Integrates with the following AWS services:
- Elastic Load Balancing, 
- AWS Lambda,
- Amazon API Gateway, 
- Amazon ELASTIC Compute Cloud, 
- AWS Elastic Beanstalk

#### X-Ray Languages

X-Ray supported languages:

* Java
* Go
* Node.js
* Python
* Ruby
* .Net

#### X-Ray Exam tips

* Understand X-Ray
* Understand what X-Ray SDK provides,
* Understand integration,
* Remember languages

------------
*Notes based mainly on Cloud Guru Course - [AWS Certified Developer](https://acloud.guru/learn/aws-certified-developer-associate-june-2018) and [AWS Whitepapers](https://aws.amazon.com/whitepapers/)*
