---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-4-notes/","updated":"2025-04-15T13:12:29.202+05:30"}
---

#CM2606

## What is a data warehouse?

>[!Definition]
>A data warehouse is basically a subject oriented, integrated, time-variant and non-volatile collection of data that provide a centralized repository for data to be unloaded into from multiple sources

The mentioned terms in the definition are like so:

- **Subject Oriented** - Basically states that the data being stored is to focus on a specific area
- **Integrated** - States that data is being integrated from multiple sources, merging it all into one consistent format
- **Time Variant** - Data being documented in the warehouse is being time stamped as its stored either explicitly or non-explicitly 
- **Non-Volatile** - The data is stored in a non-volatile state, meaning that even if power were to be cut from the warehouse the data would still retain

The reason data warehouses are used is so the data being stored in it may be analysed with ease while providing business intelligence reports covering dense trends inside a business, etc. Refer to some of the reasons to see **why data warehouses are important**:

- Offers substitute warehouse to work with instead of production level database/warehouse
- Provides a single source of truth
- Referred to for analysis and reporting (Online Analytical Processing OLAP)
- Production level warehouses are not interfered with when a data warehouse exists

Furthermore, the data provided is shared amongst company members making it a centralized storage hub that can be accessed by multiple individuals on a network.

## What is the difference between a data warehouse and database?

>[!Important]
>A data warehouse is ideal for the analysis of the contents being stored in it, in other words it is ideal for analysing and creating reports of data meaning that its data will not be constantly accessed whereas a database is ideal for transactional applications

| Characteristics    | Data Warehouse                                                                                                                                                                 | Transactional Database                                                                                        |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------- |
| **Workloads**      | Primary workload focuses on providing detailed reports for big data loaded into it                                                                                             | Primary workload focuses on transaction processing where it maps values from one endpoint to another          |
| Data sources       | Takes in data from multiple sources and integrates it                                                                                                                          | Takes in data from a single source and feeds it into the system "as-is"                                       |
| Data capture       | Data written into the warehouse in batches through the use of a batch processing algorithm                                                                                     | Data written into a database with a continuous algorithm, given that new data is almost immediately available |
| Data normalization | Denormalized data with redundant data to serve different purposes, often laid out in a star or snowflake schema                                                                | High normalized data in order to ensure quick processing                                                      |
| Data storage       | Optimized to provide high speed query responses by using column level storage                                                                                                  | Optimized to provide high write speeds in single row oriented blocks                                          |
| Data access        | Optimized to minimize I/O speeds in the warehouse, rather it maximizes its **data throughput** (refers to the amount of data that can be processed at a given time, e.g. Gb/s) | High volumes of small read operations                                                                         |
| Data               | Often stores relational data that helps transactional systems pinpoint transaction histories, etc                                                                              | Processes all kinds of data that can be structured, semi-structured and unstructured                          |
| Schema             | Designed before the development of the warehouse                                                                                                                               | Designed during the process of a transaction                                                                  |
| Price/Performance  | Fast query results at a high cost storage                                                                                                                                      | Fast query results with low cost storage by high cost processor                                               |
| Data Quality       | Highly curated data that serves as a centre of storage for truths                                                                                                              | Raw data                                                                                                      |
| Users              | Business analysts, Data Scientists/Engineers                                                                                                                                   | Business analysts, data scientists, developers and engineers                                                  |
| Analytics          | BI and similar visuals                                                                                                                                                         | Machine learning, exploratory analytics, streaming and big data                                               |

## Types of data warehouses

There are different types of data warehouses, refer to the following:

1. **Enterprise Data Warehouse (EDW)**:
	- Provides access to organization wide information that may be referred to by employees
	- Facilitates decision support services throughout the enterprise to provide the organization with a centralized store of truths
2. **Operational Data Store (ODS)**:
	- Ideal for storing operational data such as employee records
3. **Data Marts**:
	- Subset of a data warehouse that it utilized to maintain a particular department, region or business unit
	- Its called a data mart because the data stored here normally relates to a central repository of data that consists of store related data

A **data mart** is a subset of a data warehouse that offers similar features but at a much smaller scale given that the data it works with is meant to be accessed quickly and does not contain complex details. It normally consists of a subset of the data stored in a warehouse. 

In other words, a data mart is like a leaf node for a data warehouse where the data warehouse acts as the broker/aggregate for data in between an ETL pipeline and a data mart. Refer to the following image to see how data warehouses broker data to marts:

![[Pasted image 20250415125011.png\|Pasted image 20250415125011.png]]

## Data Warehouse Architectures

There are three main tiers to a data warehouse architecture:

- **Top Tier**:
	- Consists of the applications utilized to present the data in a statistical manner, etc
	- Basically any surface level tool that simply utilizes the data produced from the warehouse
- **Middle Tier**:
	- Layer where the data from the warehouse is processed into something that the top tier can understand
	- The process carried out here is known as OLAP, online analytical processing
	- In other words, this layer converts the raw data from the data tier into structured insights that can be used in the top tier
- **Data Tier**
	- Segment where the data is extracted, transformed and then loaded into the warehouse through an ETL pipeline

## Differences between a Data Warehouse and Data Pipeline

| Feature | Data Warehouse                                                                                             | Data Mart                                                                                                                  |
| ------- | ---------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Scope   | Enterprise wide scope which is application independant, consists of data from all sources                  | Application dependant, focuses on providing data to a single application from a single source routed through the warehouse |
| Data    | Consists of historical data all the way to denormalized data that came in straight from the ingestion flow | Highly denormalized data that have specified variations of data fit for a specific application or endpoint                 |
| Sources | Many internal and external sources                                                                         | Few internal and external sources                                                                                          |
| Other   | Flexible, data oriented, long life and a complex structure                                                 | Restrictive, Project oriented, Short life and multiple simple structures                                                   |
## Security in a Data Warehouse

>[!Definition]
>Given the Data Warehouses work with personally identifiable information (PII) it must maintain a security standard to ensure that none of the PII is revealed. Hence the need for data encryption rules and policies 

- Firstly, data must be classified into a category that fits its criteria
- Thereafter the data must be encrypted
- Rule/Role Based Access control polices and roles may be implemented in order to initiate levels of access and authorization
	- An example of a rule may be TLS for encrypting data in transit and AWS for encrypting static data
	- An example of roles may be admins who have full write and read access while there are endpoint users such as doctors, etc, who access the data from API's
	- Least privileges may be assigned here