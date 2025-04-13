---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-3-notes/","updated":"2025-04-13T14:51:19.074+05:30"}
---

#CM2606 

## ACID Properties of a Database

>[!Definition]
>ACID stands for Atomicity, Consistency, Isolation and Durability. These are each standards a database must achieve in order to be considered as an optimal storage medium for a business

- **Atomicity** - This property states that a transaction is a single, indivisible unit of work that cannot be split into smaller functions. Furthermore, it ensures that a transaction made within a database is always complete and not partially complete. If a transaction were only to make a portion of its content reach its destination it is to be considered as a failed transaction 
- **Consistency** - Any transaction made within one state in the database is to remain the same in another by adhering to rules and constraints. In other words, when a transaction in a database is made it must be the same from the initial state to the goal state by complying with constraints, etc
- **Isolation** - Each transaction made within the database is to be independant of another transaction as they must not interfere with each other. In other words, concurrent transactions are not to interfere with each other, hence maintaining a level of abstraction where they are invisible to each other
- **Durability** - Once a transaction is made, its changes are permanent in order to ensure that in the case of a power outage or failure the data retained in each end of a transaction is to remain the same

To conclude, **Atomicity** ensures that transactions are always complete and not partially complete, **Consistency** ensures that the initial states and goal state of a transaction remain the same by adhering to rules and constraints, **Isolation** ensures that concurrent transactions are always independant of each other and do not interfere and **Durability** states that whatever transaction made in the database makes permanent changes

## Data Storage Systems

>[!Definition]
>Mediums in which data is physically stored on such that the data accessed through them may be done so at different speeds and rates (each storage medium caters to a different purpose through variated speeds)

- **HDD's, SSD's** - Cost effective, scalable and ideal for local access
- **Network Attached Storage (NAS)** - Centralized storage in a network, ideal for shared access
- **Storage Area Network (SAN)** - Block level data access that provide a network of data storage nodes, each node is accessible by a different level
- **Big Data Distributed Storage** - Distributed and fault tolerant storage devices developed to handle and manage big data

## Data Ingestion Architecture 

>[!Definition]
>A data ingestion architecture is a design/blueprint laid out to define an ETL workflow. It specifies how the data is taken in, processed and loaded onto its target destination. Besides that, its a framework referred to in the creation of a system

![Pasted image 20250413123510.png](/img/user/pngs/Pasted%20image%2020250413123510.png)

In the image above, the following features may be noted:

- **Ingestion Flow** - Here data is collected from multiple sources and then loaded into a data lake (a place where the data is stored)
- **ETL Flow** - Extraction, transforming and loading, here data is processed and loaded into a warehouse while concurrently serving the unprocessed data into a database that may have users access it through API's
- **BI/Reporting** - Business intelligence and reporting, here there are analytics and reports made of the data processed and loaded into the warehouse such that important details may be denoted from it (e.g. trends)
- **Data Science Modelling/ Further processing** - Some of the processed data or unprocessed data may be fed into databases that may be accessed by machine learning models for the development of an AI

## Types of Data Storage in AWS

>[!Definition]
>Given that AWS provides a plethora of services, storage devices are included as one of its main components and resources. Refer to the following to see the types of mediums it offers

| Service                     | Description                                                                                                                                                                                                                                                       | Use Case                                                                                                                                                                          |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Amazon S3                   | Object based storage designed for applications that require highly available and scalable storage solutions. The data stored here is not meant to be quickly accessible for instances such as IOT device outputs, rather it is meant for loading static data onto | Data Lakes, Log Storage, Data Pipeline Endpoint, Backup and Archive                                                                                                               |
| Amazon EBS                  | This is a block storage medium provided for EC2 instances given their high performance and persistent storage capabilities. **Block storage means that data is stored in fixed-size chunks known as blocks**, each block has an identifier                        | Relational Database Storage, Application storage, EC2 boot volumes, Container storage (e.g. Docker based application                                                              |
| Amazon Elastic Files System | This is a managed network files system, its offers a shared storage medium for groups of EC2 instances that enable multiple users to access the same storage medium                                                                                               | Shared Files Systems, Big Data Analytics, Web Serving (e.g. Shared static content), Media process                                                                                 |
| Amazon Glacier              | This is a secure long term storage medium ideal for data archiving and similar instances given that its data is not meant to be accessed constantly, rather rarely instead                                                                                        | Data Archives, Regulatory Archives (archival storage for financial and regulatory compliance, ensuring long term data retention), Document Archives, Substitute to magnetic tapes |
To conclude, each storage medium has a set of different implications, refer to the following:

- **S3** - Ideal for immediate data storage solutions with fast access
- **EBS** - Ideal for booting EC2 instances or similar operations
- **EFS** - Ideal for shared access based storage networks
- **Glacier** - Ideal for long terms storage given its low latency access rates, etc

## Apache Spark

>[!Definition]
>Apache spark is an **open source distributed computing engine** that focuses on big data processing and analytics, etc. It is ideal for running complex tasks on the cloud given its distributed computational power, hence its ability to execute these tasks with ease

Spark is a part of the Hadoop ecosystem as it takes care of big data related projects. One of the main features of spark is the fact that it has in-memory computing, hence enabling it to complete complex tasks. 

**Hadoop** is an open source framework for storing and processing large datasets across multiple computer clusters. It has two main components:

- **HDFS (Hadoop Distributed File System)** - A distributed file system that stores data across multiple machines
- **MapReduce (Processing Engine)** - A programming model utilized by Hadoop to process data in parallel, it does so by **Mapping** the data (filtering and sorting) and then **Reduces** it (summarizes and shortens)

Spark is a substitute to Hadoops current MapReduce function as it offers to run processes in parallel with the added feature of **in-memory** processing. So, there are some features to consider when utilizing Spark instead of Hadoops map reduce model:

| Feature    | Hadoop / Map Reduce | Spark |
| ---------- | ------------------- | ----- |
| Data Loads |                     |       |
