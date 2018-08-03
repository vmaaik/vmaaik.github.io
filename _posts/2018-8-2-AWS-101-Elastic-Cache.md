---
layout: post
title: AWS 101 - Elastic Cache - Draft
---

Elastic Cache is a web service that makes it easy to deploy, operate, and scale an in-memory cache in the cloud. The service improves the performance of the web application by allowing you to retrieve information from fast, managed, in-memory caches, instead of relying entirely on slower disk based databases. 

You do not have to constantly querying the same information your DB

### Notes
#### What is Elastic Cache

Amazon Elastic Cache can be used to significantly improve latency and throughput for many ready-heavy applications workloads( such as social networking, gamin, media sharing and Q&A portals) or computer intensive workloads (such as recommendation engine). 

Caching improves application performance by storing critical pieces of data in memory for low-latency access. Cached information may include results of I/O intensive database queries or the results of computationally-intensive calculations. 

The more you cache the less load you put on your DB and the more free your DB is. 

#### Types of Elasticache

 - Mamcached - a widely adopted memory object caching system. ElasticCache is protocol compliant with Memcached, so popular tools that use today with existing memcached environments will work seamlessly with the service. 
 
 - Redis - A popular open source in-memory key value store that supports data structures such as sorted sets and lists. ElasticCache supports Master/Slave replication and Multi-AZ which can be used to achieve cross AZ redundancy
 
 **Exam tip** - If you need Multi-AZ access you wanna use Redis, if you don't concern about redundancy you can use Memcached.
 
Redis
Although both memcached and Redis appear similar on the surface( in that they are both in-memory key stores) they are actually quite different in practice. because of the replication and persistence features of Redis, ElastiCache manages Redis more as relational database. Redis ElasticCache clusters are managed as stateful entities that include fail-over, similar to how Amazon RDS manages database fail-over. 
 
 
Memcahced
Because memcached is designed as a pure caching solution with no persistence, ElastiCache manges memcached nodes as a pool that can grow and shrink, similar to an Amazon EC2 Auto Scaling Group. Individual nodes are expandable, and ElasticCahce provides additional capabilities here, such as automatic node replacement and Auto Discovery. 

Mamcached - Use Cases
- if the **object caching is your primary goal**, for example to offload your database, 
- if you interested **simple caching model as possible**, 
- running large cache nodes, and require multi-threaded performance with utilization of multiple cores
- if you want to **scale your cache horizontally** as you grow.


Redis - Use Cases
- more **advanced data types, such as lists, hashes, sets**
- doing **sorting and ranking datasets in memory**, such as with leader-boards
- if **persistence** of key store is important
- if you want to use multiple AWS Availability zones with fail-over **Multi-AZ**
- Pub/sub capabilities are needed. 
 
**Exam tip** - if in scenario is leader-board always chose Redis

**Exam Scenario**

You will be given a scenario where a particular database is under a lot of stress/load. You may be asked which service you should use to alleviate this. 

Elasticache is a good choice if your database is particularly read-heavy and not prone to frequent changing. (DB)

Redshift is a good answer if the reason your database is feeling stress is because management keep running OLAP transaction on it etc. (Warehousing) 

------------
*Notes based mainly on Cloud Guru Course - [AWS Certified Developer](https://acloud.guru/learn/aws-certified-developer-associate-june-2018) and [AWS Whitepapers](https://aws.amazon.com/whitepapers/)*
