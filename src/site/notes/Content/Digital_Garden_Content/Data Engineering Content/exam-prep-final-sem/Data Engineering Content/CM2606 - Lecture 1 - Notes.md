---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-1-notes/","updated":"2025-04-12T18:49:10.790+05:30"}
---

#CM606

## What is data engineering?

>[!Definition]
>It refers to the process of developing pipelines and infrastructures to handle data flows and intakes such that it is properly optimized and reaches its designated location in an optimized time period. Furthermore, data engineering includes report generation, etc

Some of the key components in data engineering include:

- Security Implementations
- Data Monitoring
- Storage Management
- Processing Data
- Maintaining Pipelines

Some of the biggest challenges faced by data engineers include how they are to accumulate data from multiple sources while moving and storing it in a secure and optimized fashion, hence making data engineering include the same functionalities as a Devops engineer, check the [[Content/Digital_Garden_Content/Data Engineering Content/Machine Learning Operations\|Machine Learning Operations]] note. 

To conclude, data engineers handle multiple variations of handling and managing data such that it can be monitored, trends can be analysed and developed and pipelines may be staged to automate tasks, etc
## What is big data?

>[!Definition]
>Big data refers to large data sets that are meant to be computationally processed due to how vast and big it is. Its domains vary from healthcare to business growth management, etc

Some solutions in big data include:

- Retail
- Transport
- Banking and Finance
- Tele-communications
- Healthcare

In data engineering, one of the most common manners of implementing and staging solutions as such is through the use of Amazon Web Services (**AWS**). It is a platform that offers services that provide users access to a series of virtual and cloud based resources and tools. Some use cases that actively utilize these services include:

- Netflix
- Facebook
- Instagram

## What is a data eco-system?

>[!Definition]
>A data eco-system is basically a network of interconnected components that vary from individuals to processes and technologies. The interconnected resources are meant to provide insights into how the system is running

In an organization, an eco-system refers to:

- **How the data is captured stored and processed**
- **How the captured data is used to generate insights into the system**
- **How the stakeholders are to act on the generated insights**

What makes eco-systems optimal for businesses is the fact that it is unaffected by the external world and is solely built to manage the businesses systems. Furthermore, it is scalable and easy to add components to. The components of a data eco-system include:

- **Data Capture**: E-commerce Sites, Web Applications, Social Media Applications, etc
- **Storage**: Databases, Data warehouses and Data lakes
- **Process/Insight Generation**: Sentiment Analysis, Trend Analysis, Performance analysis
- **Actions**: Strategic/ Operation business decision making

## What is AWS?

>[!Definition]
>AWS is a cloud, on-demand, service platform that offers services and solutions that come in the form of computing solutions. This includes, storage, monitoring and processing functions that include security policies as well

The reason AWS is called "on-demand" is due to the fact it provides immediate services that come with a "pay-as-you-go" option given that the costs incurred by the use of their resources are scaled based on how much time is spend using their resources and how much of their resources are utilized. The main components of AWS include:

- Computational Resources (e.g. EC2, Sagemaker, etc)
- Storage Solutions (e.g. S3, Redshift)
- Analytics tools (e.g. Glue, Athena, Cloudwatch for resource monitoring and general purposes)
- Security Implementations (e.g. IAM Roles and policies)

One of the key features of AWS is its regional availability, based on where a user is they may switch regions to something they are closer to for lower latency. 

## AWS Databases

Some of AWS's database include the following:

| Database Type | Description                                                                                                                                                                                                             | AWS Service                                   |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------- |
| Relational    | Basic ERP tools implement relational databases to manage their systems                                                                                                                                                  | Amazon Aurora, Amazon RDS, Amazon Reshift     |
| Key-Value     | Similar to dictionaries, these database types are normally implemented for high traffic applications such as social media apps or gaming applications                                                                   | Amazon DynamoDB                               |
| In-memory     | Database with in memory caching for session management, applications that have leaderboards, for example, may utilize this                                                                                              | Amazon Elasticache, Amazon MemoryDB for Redis |
| Document      | Content management and user profiles                                                                                                                                                                                    | Amazon DocumentDB                             |
| Wide Column   | Meant for applications that implement fleet management, or route optimization given that it can store data in columns rather than rows since each row consists of long stretches of data                                | Amazon Keyspaces                              |
| Graph         | Implemented for fraud detection, social networking and recommendation engines given that it stores data as interconnected nodes so its easier to map data from one node to another hence its content based optimization | Amazon Neptune                                |
| Time Series   | Ideal for real time data analysis given that it is capable of time stamping real time data that is taken in by the system. It has fast write and retrieval speeds                                                       | Amazon TimeStream                             |
| Ledger        | Optimal for record based storage systems as it is ideal for storing specialized and immutable data that provides information of records of data over time                                                               | Amazon Ledger Database Service                |
