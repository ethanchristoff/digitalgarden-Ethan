---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-5-notes/","updated":"2025-04-17T13:12:28.000+05:30"}
---

#CM2606

## What is an Ingestion flow?

>[!Definition]
>Refers to the process of pulling data from multiple data sources to then curate into a single merged source such that it may then be off loaded into a warehouse, lake house or database

In an ETL pipeline, the process of collecting data from a source as such is known as an ingestion flow. Here data is collected from multiple sources, processed and then unloaded into a warehouse.

## What is a data processing system?

>[!Definition]
>Its a collection of software and hardware features when put together process a raw input into structured and more understandable information. These systems represent life cycles that take place is a system from data collection to analysis and representation

An example of a processing system includes:

- **Transactional Processing Systems**
- **Data Warehousing Systems**
- **Machine Learning Pipelines**

So, given the following systems each of them may utilize different processing systems in order to minimize the utilization of processing power and resources. There are two main forms of processing data:

- **Batch Processing** - Processing method where data is processed in batches in intervals to process large chunks in an efficient and a resource un-intensive manner, ideal for processing big data and offers a lower cost with higher reliability due to batch optimization. E.g. ETL pipelines, log processing, billing data, etc
	- Processes data in batches in given intervals
	- Efficient for processing large datasets over time
	- Provides detailed reports from each batch
	- Inexpensive and efficient
- **Real Time Processing** - Processes raw data as it is fed into the system and immediately provides and output for the processed data, ideal for IOT device data analysis, stock trading, etc
	- Ideal for tracking real time data
	- Processes data immediately as it comes
	- Provides immediate responses which may include unstructured data
	- Expensive but scalable in an efficient manner

Besides the mentioned two there are two more processing methods to be considered:

- **Stream Processing**:
	- Processes data in motion continuously while enabling low-latency real time analysis of data that may be fed in from IOT devices, etc
	- Ideal for reactive systems that make active decisions on the go
	- Does not operate on the entire dataset, rather it does so one row at a time
	- Example use cases include:
		- Fraud detection
		- Stock analysis
		- Application monitoring 
- **Hybrid Processing**:
	- A combination of batch and stream processing by ingesting some stream data that is processed as it comes but row by row, while storing some data in rest and applies batch processing to that
	- For example, logs of past user interactions may be stored and processed in batches while active users may be processed using stream processing

Main differences between batch streaming, stream processing and hybrid processing:

|            | Batch                                                                                                       | Stream                                                                                                         | Hybrid                                                                                                                                                   |
| ---------- | ----------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Difference | Processes data in batches with intervals in between and does so in large chunks to provide detailed reports | Processes data as it is fed into the system while doing so row by row instead of processing the entire dataset | A combination of batch and stream processing where it processes real time data using stream processing and stored historical data using batch processing |
## What should you consider when choosing batch and real time processing?

>[!Important]
>Some of the more important factors you should consider include the size of the dataset being produced and the velocity (speed) in which it is being received, thereafter the expected latency of the data set should be considered as well (e.g. Stock market response should be immediate)

### Data Volume and Velocity

Here you should consider how big the dataset is (volume) and how fast/quickly it is being fed into the system (velocity). When considering these two it may be concluded that:

- **High Volume and Low Velocity** - Batch Processing due to large volume size and low velocity
- **Low Volume and High Velocity** - Real time processing, given that the dataset is small but the speed at which the system is receiving it is fast

### Latency

Here you should consider the time between the data arrival and the processing time, like should the system process the data quickly and provide an immediate response or is a delay allowed. It may be stated that:

- **High Latency** - Batch processing given that the time in which the data is received and then processed can be fairly long given that the timing does not necessarily matter
- **Low Latency** - Real time processing given that the response is expected to arrive immediately and the time between arrival and processing should be as small as possible 

### Applications

The application in which the processing system is implemented must be considered given that some applications do not require immediate processing while others do, consider the following:

- Batch processing lends itself to periodic workloads, hence leading to occasional usages thus making an application that requires periodic processing times utilize a batch processing system better than a real time processing system which is more inexpensive and efficient (e.g. ETL pipelines that run weekly)
- Real time processing tends to process data immediately and is expected to process low volumes of data that have a low latency, hence making real time systems more optimal for the given context (e.g. fraud detection or anomaly detection or spam detection)

## AWS Services

>[!Important]
>AWS services are basically an array of tools and services that provide a resource for a limited period of time or with scalable limits

Some of AWS services include:

- **Amazon EMR** - Scalable cluster solution for batch processing on Hadoop
- **Amazon Kinesis** - Streaming data platform for real time data processing and ingestion
- **Amazon Redshift** - Fats data warehouse solution for big data storage, etc
- **Amazon Lambda** - Serverless invocation service that offers compute services for real time events

## What is AWS Lambda?

>[!Definition]
>AWS Lambda is a serverless computing service that offers invocations when certain events are triggered to alert a user on that event occurring, or similar functions. It may even create functions that execute algorithms to execute another sub service
>

Lambda refers to compute times to bill users in a code, the longer the execution time of a code the higher the bill. However, it does not require a designated structure to run on rather it requires a invocation to be executed. When idle, it does not bill the user given that it is not executed. 

To conclude, lambda is an event driven process that carries out functions when invoked by another function such as uploading data into an S3 bucket.

## What is Apache Beam?

>[!Definition]
>Beam is an open source unified model responsible for batch and stream processing data in parallel pipelines, hence making it an orchestration tool of sorts

Similar to Spark, it is a distributed computational network of machines called runners that execute tasks parallel to each other in code by executing them through lines of code. It can then offload the processed data into machines that are a part of clusters in spark.

The difference between beam and spark is that spark is a distributed computing engine responsible for big data processing by processing data in clusters of machines called worker nodes. Whereas Beam is a programming model that defines data processing pipelines that can run on processing engines such as Spark.

Beam is the code used to run algorithms parallelly using stream and batch processing that is then executed on a machine framework such as Spark. So Spark is the engine Beam's parallel code is runs on through the use of "runners".