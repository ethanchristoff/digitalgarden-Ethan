---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-7-notes/","updated":"2025-04-16T18:53:34.614+05:30"}
---

#CM2606

## What is a Data Catalogue?

>[!Definition]
>Data cataloguing refers to the process of cataloguing data and organizing it according to their similar attributes. It ensures that some datasets comply with rules and constraints while enforcing transparency and usability

Data transparency refers to making the data transparent by explicitly stating what its meant to be used for and why it is to be collected which in this context is by cataloguing it with other data values with similar attributes

## What is data lineage?

>[!Definition]
>It refers to the process of tracking the path of data, hence the name lineage. You would be considering where the data is collected from, where it is processed and where it is outputted into

**OpenLineage** is a system that helps track and organize how data is collected, processed and stored. Refer to the following diagram:

![Pasted image 20250416084132.png](/img/user/pngs/Pasted%20image%2020250416084132.png)

You can see here how data is collected from a source and how it is unloaded as a dataset. The following points elaborate on what each value means here:

- **Source** - Place where the data comes from (e.g. MYSQL, KAFKA, etc)
- **Dataset** - Table or stream of data from the source
- **Dataset Version** - A specific snapshot of a dataset, hence creating a version of it
- **Job** - Refers to a process that is carried out to carry out a function on the data
- **Job Version** - Snapshot of a job that creates a history of changes made to the jobs (e.g. can be carried out with a batch or stream processing algorithm)
- **Run** - A job that is run once and constantly 
- **DbTable/Stream** - The type of data being collected is either from a database or streaming platform

Some common issues experienced by using OpenLineage include:

- **Lack of standardization** - Values do not have a standard deviation of 1 or mean of 0
- **Difficult in tracking data lineage** - Hard to pinpoint the source and flow of data
- **Integration with diverse tools and platforms** - Difficult to integrate this system with common tools and platforms

## Distributed Systems

>[!Definition]
>A distributed system is a collection of independant computers working together to solve a common problem by sharing data and resources, hence the name "distributed"

Some of the key benefits of using a distributed system include:

- Improved processing power due to combination of multiple machines resources
- Highly scalable given that you can easily add a new machine to the system
- Highly available, hence providing fault tolerance and avoiding unnecessary down times while reducing redundancy
- Can execute tasks concurrently and in parallel, hence the term parallelism 

There are also NoSQL distributed systems which is basically a database architecture that is designed for flexibility and scalability. The main characteristics of a NoSQL database is that:

- It is Schema-Less which support evolving data models
- Horizontally scalable by adding nodes to handled increasing volumes of data
- Highly available 
- Diverse data model that can support key value, graph and document databases

## Cap Theorem

>[!Definition]
>It is a fundamental logic and theory in distributed computing that states (C) consistency where every node can see what is happening in each other node, (A) availability where the system always responds to requests and (P) partition tolerance which states that the system continues to work even if there are communication issues between nodes

CAP theorem is a fundamental theory in distributed systems that state the following terms:

- **Consistency** - States that every node can see what is happening in the other nodes, this means that if a change is made in one node it will be replicated in every other node
- **Availability** - States that the system must always be available and respond when requested even when there is an issue in the system
- **Partition Tolerance** - States that even when there are issues communicating between nodes, the system will still respond

>[!Important]
>A network partition is basically when a part of the network is partitioned off preventing a node from communicating with the rest of the server, so partition tolerance states how well a server can handle a single node being cut off from communicating with the rest of the network

To conclude, CAP theorem refers to a theory every distributed system must adhere to in order to ensure that it functions as a proper system. The main features are:

- **Consistency - Ensures that every node in the system can see when data changes in another node**
- **Availability - Clients can actively update and change data even if a node fails
- **Partition Tolerance - The system is able to operate even if the network fails (e.g. If a system is distributed regionally, if even one region has issues communicating the system will still respond)**

It must be stated that only two of the three properties can work together in CAP theorem:

- **CA** - A system can be consistent and available but cannot tolerate miscommunications between partitions
- **CP** - A system can be consistent and partition tolerant but it cannot always be available if a node is down
- **AP** - A system can both be available and its partitions can tolerate faults with communications but it cannot be consistent with its data meaning that not all nodes will know if a change is made in one node

It must be understood that CAP theorem is a theory that issues trade offs for the sake of maximizing either consistent data at the cost of unavailability within a system or making the system as available as possible at the cost of inconsistent data.

![Pasted image 20250416183917.png](/img/user/pngs/Pasted%20image%2020250416183917.png)

An example of a system that is more available than consistent is Amazon's DynamoDB, a NoSQL database that is ideal for quick transactions that can be used as a gaming backend.

In the case of focusing on just consistency and availability it would mean that:

- If a single partition break were to occur, the entire system would be unavailable to ensure 100% consistency
- Due to the above feature, data values will always be consistent and available as long as there are no partition breaks
- If there are any partition breaks, then the system will not work

>[!important]
>Partition breaks basically mean that if there is a single break in the system, it should still work but in the case of something where both consistency and availability are maximized then it is to be assumed that if there is even a single partition break the entire system will not work