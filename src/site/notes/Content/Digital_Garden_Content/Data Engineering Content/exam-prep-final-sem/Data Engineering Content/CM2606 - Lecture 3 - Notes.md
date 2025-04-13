---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-3-notes/","updated":"2025-04-13T12:49:37.191+05:30"}
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

| Service    | Description                                                                                                                                                                                                                                                       | Use Case                                                                                                               |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Amazon S3  | Object based storage designed for applications that require highly available and scalable storage solutions. The data stored here is not meant to be quickly accessible for instances such as IOT device outputs, rather it is meant for loading static data onto | Data Lakes, Log Storage, Data Pipeline Endpoint, Backup and Archives                                                   |
| Amazon EBS | This is a block storage medium provided for EC2 instances given their high performance and persistent storage capabilities. **Block storage means that data is stored in fixed-size chunks known as blocks**, each block has an identifier                        | Relational Database Storage, Application storage, EC2 boot volumes, Container storage (e.g. Docker based applications) |
