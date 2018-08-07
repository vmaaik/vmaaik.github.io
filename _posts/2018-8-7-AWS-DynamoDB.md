---
layout: post
title: DynamoDB | Amazon Web Services Notes 
---

Amazon DynamoDB is a fast and flexible NoSQL database service for all applications that need consistent, single-digit millisecond latency at any scale. It is a fully managed database and supports both document and key-value data models. Its flexible data model and reliable performance make it a great fit for mobile, web, gaming, ad-tech, IoT, and many others applications. 

* Stored on SSD storage (fast)
* Spread Across 3 geographically distinct data centers (avoids failure), 
* Choice of 2 consistency models:
	* Eventual Consistent Reads (Default)
	* Strongly Consistent Reads

**Eventual Consistent Reads**
Consistency across all copies of data is usually reached within a second. Repeating a read after a short time should return the updated data(Best Read Performance)

**Strongly Consistent Reads**
A strongly consistent read returns a result that reflects all writes that received a successful response prior to the read.

### DynamoDB structure

* Tables
* Items (row of data)
* Attributes (columns)
* Supports key-value and documents data structure
* Key = name of the data, value = data itself
* Document can be written in JSON, HTML or XML

### DynamoDB - Partition Key

* DynamoDB stores and retrieves data based on a Primary Key
* Partition Key - unique attribute e.g. user ID
* Value of the Partition key is input to an internal hash function which determines the partition or physical location on which the data is stored
* if you are using Partition Key as your Primary Key, then no two items can have the same Partition Key

### DynamoDB - Composite Key (partition Key + Sort Key) 

Partition key and sort key: Referred to as a composite primary key or hash-range key, this type of key is composed of two attributes. The first attribute is the partition key, and the second attribute is the sort key.

* Allows you to store multiple items with the same Partitions Key
* Example:
	* Partition Key - User ID, Sort Key timestamps of the post. 2 items may have the same Partition Key, but must have a different Sort Key. 

### DynamoDB - Access Control

* Authentication and AC to DynamoDB is managed via AWS IAM
* You can create an IAM user within your AWS account which has specific permissions to access and create DynamoDB tables
* You can create an IAM role with enables you to obtain temporary access keys the can be used to access AWS services like DynamoDB.
* You can also use a special IAM Condition to restrict user access to only their own records