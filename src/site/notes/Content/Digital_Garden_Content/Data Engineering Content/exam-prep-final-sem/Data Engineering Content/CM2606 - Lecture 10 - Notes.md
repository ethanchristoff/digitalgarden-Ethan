---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-10-notes/","updated":"2025-04-18T08:59:59.148+05:30"}
---

#CM2606

## What is Amazon QuickSight?

>[!Definition]
>Its a scalable business intelligence service offered by Amazon to help provide visuals for complex or large datasets

It a service that provides users with the ability to generate detailed visuals to represent and analyse data. Some of the visualizations offered by QuickSight include:

![Pasted image 20250418074728.png](/img/user/pngs/Pasted%20image%2020250418074728.png)

## What is Athena

>[!Definition]
>Athena is a serverless query service that is capable of retrieving data from S3 buckets using standard SQL queries. What makes this an optimal service is the fact that users do not have to setup an infrastructure for Athena as it run as a serverless service

To summarize, Athena is simply a service offered by AWS that provides serverless SQL queries that can be made on S3 buckets to retrieve information from them. Thereafter, the collected data can be visualized as well through the use of a service like QuickSight.

The average workflow to collect data from a source and display it goes like so:

`Collect data using athena -> Unload into data lake -> use quicksight`

Some alternative tools that can be used to represent data include:

- **Grafana** - Open source analytics and visualization platform
- **Amazon Athena** - Serverless interactive query service utilizing SQL
- **Amazon Managed Grafana** - Fully managed Grafana service by AWS

When it comes to visualizing visualization alternatives, Grafana poses an open source and scalable alternative that can be used for business intelligence. However, Microsoft's PowerBI is one of the most powerful visualization BI tools to exist.

## What is PowerBI

>[!Definition]
>It's a business intelligence tool capable of visualizing and analysing large streams of data with ease. It may be used to create detailed reports of trends and similar features in the data collected
>

PowerBI is also capable of collaborative works as you can manage to create detailed reports, collaboratively, with other members. Some of the benefits in using PowerBI include:

- **Improved Decision Making** - based on reports provided by BI, more refined decisions may be made
- **Increased Efficiency**
- **Enhanced Communication**
- **Better Collaboration**
- **Increased Productivity**

Besides using tools that are exclusive to detailed report development, there are extensions an libraries that may be utilized by applications to create interactive graphs such as D3 JavaScript.

## What is D3 JavaScript?

>[!Definition]
>Its a java script library utilized for creating interactive and dynamic data visualizations in web browsers. Its flexible, data driven and optimized for web pages

What makes D3 java scripts so useful is that fact that it can represent data on websites with ease while providing detailed reports on large strands of data.

## What is CI/CD?

>[!Definition]
>"Continuous Integration/Continuous Deployment" refers to a software development practice carried out by developers such that they can continuously automate the process of deploying, testing and implementing applications
>

The automated process here states that when a submission is made into a repository by the developer (CI) it is then pushed into the process of building, testing and then deploying (CD) their commit in an automated manner. The AWS pipeline for CI/CD may be implemented like so:

![Pasted image 20250418080402.png](/img/user/pngs/Pasted%20image%2020250418080402.png)

In a CI/CD pipeline there are multiple stages a commit must go through before being pushed into production, a typical workflow would be followed like so:

1. **Source Code Committed** - The code is committed onto a version control system like GIT
2. **Build Formed** - Turned into deployable artifact like container or jar file
3. **Test Carried Out** - Code is tested to ensure that it works
4. **Deployed New Commit** - Code is finally deployed into production
5. **Monitored** - Application is monitored for errors through Cloudwatch, etc

In order to implement a pipeline as such, AWS offers a series of developer tools that are capable of doing so, the following refer to the available tools:

- AWS Code Commit
- AWS Code Build
- AWS Code Pipeline
- AWS Code Deploy
- Amazon Elastic Container Registry (ECR) - Container management registry which enables AWS to containerize, for example docker container images, code and applications
- AWS CodeStar - Deployment service for applications

## AWS Cloudwatch vs Cloudtrail

>[!Definition]
>Cloudwatch is a resource monitoring service, it tracks and provides detailed reports of services being utilized by an instance, as an example, or similar resources. Cloudtrail on the other hand tracks user activities and API calls within your AWS account

Cloud watch is a service that provides metrics to monitor AWS resource consumptions and invocations while collecting logs and event timestamps. It provides a visual interface for these metrics. Alarm systems can be made to alert users of when a resource is either being overused or underused, etc.

Cloud trail is a service that provides metrics to track user activities with an account. It traces which user did which activity within a log file while tracing back when the event took place. It can provide audit logs for which event took place when while helping users reconstruct events in the case of suspicious activities.

| Feature                                                | CloudWatch                           | CloudTrail                          |
| ------------------------------------------------------ | ------------------------------------ | ----------------------------------- |
| Tracks user access related information                 | No                                   | Yes                                 |
| Forms auditable logs for when users accessed a service | No                                   | Yes                                 |
| Provides metrics to monitor resource useage            | Yes                                  | No                                  |
| Useful for performance monitoring                      | Yes                                  | No                                  |
| Useful for security auditing and compliance reporting  | No                                   | Yes                                 |
| Common Data Types                                      | Numbers, Textual Data and occurences | API calls and user activity details |

## What is a UDF?

>[!Definition]
>User defined functions are functions developed and created by users to minimize redundancy by reusing code and to maximize efficiency

UDF's can be used by Pyspark to provide reusable functions within a spark interface. It is done so by **creating a function in python syntax, wrapping it in PySpark SQL and then registering it as a UDF so that it can be utilized in a dataframe**.

The reason UDF's are rarely used and considered is due to the fact that they are expensive and complicated to implement, hence making it a last resort to implement unless absolutely necessary.

## What is a data lakehouse?

>[!Definition]
>It is a combination of both data warehouses and data lakes as it is capable of ensuring the same scalable capabilities of both storage services

A data lakehouse is capable of offering storage services similar to a warehouse while also offering a stage where the raw data may be stored in a lake. Furthermore, it offers additional features such as transactions within the lakehouse and the ability to manage data with more ease.

So, a data lakehouse defers to a data lake like so:

| Feature      | Data Lake                                 | Data Lakehouse                                                 |
| ------------ | ----------------------------------------- | -------------------------------------------------------------- |
| Data Type    | Raw (Unstructured + Structured) data      | Same                                                           |
| Storage      | Cheap and scalable (e.g. S3)              | Same                                                           |
| Schema       | Schema-On-Read                            | Schema-On-Write (more structured)                              |
| Query Speeds | Slow (Requires pre-processing)            | Faster (Optimized for analytics)                               |
| Transactions | No support                                | Has support (ACID support via Delta Lake, Apache Iceberg, etc) |
| Data Quality | Low Governance                            | High Governance + Reliability                                  |
| Use Cases    | Data Science and storage related purposes | Analytics + BI + Machine Learning                              |

A simple analogy that may be referred to represent how lakehouses, lakes and warehouses defer from each other may be referred to from the following:

- **Data Lake**: A huge oil barrel - it stores everything raw
- **Data Warehouse**: A clean refinery - only refined oil (data) is stored
- **Data Lakehouse**: A refinery _next to_ your barrel - you can **store raw data** but also **refine and analyse it quickly**