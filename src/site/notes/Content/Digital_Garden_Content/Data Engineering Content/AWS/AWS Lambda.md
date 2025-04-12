---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/aws/aws-lambda/","updated":"2025-04-09T19:27:31.136+05:30"}
---

#fundamentals #aws

## What is AWS Lambda?

>[!important]
>Lambda is a serverless invocation/computer service capable of executing a simultaneous function when invoked without the need to be hosted on a server. It can carry out functions that normally act as an alert system (e.g. monitoring instance performance with cloudwatch to ensure limited usage)

How lambda works is by simply running itself off of a container. Whenever a new function is created, a container with all its pre-requisites are made as well, refer to the following steps to see what happens when a new function is created:

1. When a function is created Lambda packages itself into a new container
2. It executes that container in a **multi-tenant cluster** of machines managed by AWS
	1. Before executing the function RAM and CPU processing power is allocated to the container
	2. The user is billed based on the ***amount of RAM allocated multiplied by the amount of time spent running***

## What makes Lambda so important?

Given the fact that it is a serverless function that does not run off an instance you're hosting makes it ideal for a serverless architecture. For example, if you wish to see when an upload is made to an S3 bucket you can execute a lambda function to notify you about it.

Lambda fills the primary role of the compute service on AWS. It also integrates with many other AWS services and, together with API Gateway, DynamoDB and RDS, forms the basis for Serverless solutions for those using AWS. Lambda supports many of the most popular languages and runtimes, so it’s a good fit for a wide range of Serverless developers.

## What are some common use cases for Lambda?

When it comes to Data processing. Lambda functions are optimized for event-based data processing. It is easy to integrate AWS Lambda with data sources like Amazon DynamoDB and trigger a Lambda function for specific kinds of data events.

For example, you could employ Lambda to do some work every time an item in DynamoDB is created or updated, thus making it a good fit for things like notifications, counters and analytics.

- Monitoring a servers functionality periodically
- ETL pipeline monitoring to ensure that data is coming in or going to a source on time
- Notification systems
- Task automation through deliberate invocations 