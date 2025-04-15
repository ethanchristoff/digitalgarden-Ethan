---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-5-notes/","updated":"2025-04-15T15:16:08.590+05:30"}
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

