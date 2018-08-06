---
layout: post
title: AWS 101 API Gateway - Draft
---

An API stands for an Application Programming Interface. 

### Types of APIs?

- REST APIs (REpresentaional State Transfer), uses JSON
- SOAP APIs (Simple Object Access Protocol), uses XML

### What is API Gateway -

Amazon API gateway is a fully managed service that makes it easy for developers to publish, maintain, monitor and secure APIs at any scale. With a few clicks in the AWS Management Console, you can create an API that acts as a front door for applications to access data, business logic, or functionality from your back-end services, such as applications running on EC", code running on AWS Lambda, or any web app. 

### What can API Gateway do?

- Expose HTTPS endpoints to define a RESTful API, 
- Serverless-ly connect to services like Lambda & DynamoDB (no EC2 instance),
- send each API endpoint to a different target, 
- Run efficiently with low cost, 
- Scale effortlessly, 
- Track and control usage by API key, 
- Throttle requests to prevent attacks,
- Connect to CloudWatch to log all requests for monitoring, 
- Maintain multiple versions of your API. 

### How do I configure API Gateway?

* Define API (container)
* Define Resourced and nested Resources(URL paths)
* For each Resources:
	* select supported HTTP methods (verbs),
	* set security, 
	* Choose target (such as EC2, Lambda, DynamoDB), 
	*Set request and response transformations, 
* Deploy API to a Stage (different stages test, prod)
* Can use custom domain 
* Now supports AWS Certificate Manager: free SSL/TLS certs!

### What is API caching? 

You can enable API caching in Amazon API Gateway to cache your endpoint's response. With caching, you can reduce t he number of calls made to your endpoint and also improve the latency of the requests to your API. When you  enable caching for a stage, API Gateway caches responses from your endpoint for a specified time-to-live (TTl) period in seconds. API Gateway then responds to the request by looking up the endpoint response from the cache instead of making a request to your endpoint. 
- MC Donald's cache system.

### Same Origin Policy

In computing, the same-origin policy is an important concept in the web application security model. Under the policy, a web browser permits scripts contained in a first web page to access data in a second web page, but only if both web pages have the same origin. 

This is done to prevent Cross-Site Scripting (XSS) attacks. 
* Enforced by web browsers,
* Ignored by tools like PostMan and curl

### Cross-Origin Resource Sharing (CORS)

CORS is one way the server at the other end (not the client code on the browser) can relax the same-origin policy. 

Cross-origin resource sharing is a mechanism that allows restricted resources (e.g. fonts) on a web page to be requested from another domain outside the domain from which the firs resource was served. 

* Browser makes an HTTP OPTIONS call for a URL
	* OPTIONS is an HTTP method like GET, PUT, and Post
* Server returns a response that says:
"These other domains are approved GET this URL."

* Error - "Origin policy cannot be read at the remote resource?"
You need to enable CORS on API Gateway.

### Exam tips:

- remember what API Gateway is at high level,
- API Gateway has caching capabilities to increase performance
- API Gateway is low cost and scales automatically, 
- You can throttle API Gateway to prevent attacks, 
- You can log results to CloudWatch,
- If you are using JS/AJAX that users multiple domains with API gateway, ensure that you have enabled CORS on API Gateway
- CORS is enforced by the client.

------------
*Notes based mainly on Cloud Guru Course - [AWS Certified Developer](https://acloud.guru/learn/aws-certified-developer-associate-june-2018) and [AWS Whitepapers](https://aws.amazon.com/whitepapers/)*

