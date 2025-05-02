---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-final-notes-and-essential-reading/","updated":"2025-04-22T23:55:31.000+05:30"}
---

#CM2606 

# Final Notes
## What is a dimension table?

>[!Definition]
>Simply put, its a table that consists of details and attributes that define an entity or item that may be referred to in a fact table

Dimension tables normally include:

- Details about a foreign key in a fact table which may provide extra information
- Details that define the ID and attributes of the item stored in the fact table
- Provides context on what a certain foreign key may be referring to through the use of a dimension table

To conclude, a dimension table provides context on what a fact is in a fact table by further elaborating on it and explaining it.

## What is a fact table?

>[!Definition]
>Normally a table that is used to hold transactional data that consist of a **record of events** which take into record quantifiable information and data that refer to a single event or transaction that occurs in the system

Take for example an invoice, it can include the details of how many of a product were sold and which store it had originated from, however it does not store the more descriptive details that provide contexts for these tables. The following are some common points and attributes you would see in a fact table:

- Transactional data
- Foreign Keys (e.g. P01 - ID for a product)
- Quantities 

So, fact tables consists of facts that define the attributes of an event that takes place within the system

## What is an aggregate table?

>[!Definition]
>Basically a table that consists of aggregate values that can be used for quick query searches or similar contexts. In other words, aggregate tables store summarized values

As the name implies, aggregate values are stored in the table in order to enable SQL querying systems to make shorter queries by accessing tables like this (e.g. Monthly Sales). Most attributes stored in aggregate tables include:

- Numerical values
- Summations and summaries of numerical values from other tables

# Essential Reading

## How does Spark run on a Cluster?

>[!Definition]
>Sourced from [The Definitive Guide - Big data processing made simple](https://github.com/letthedataconfess/Data-Engineering-Books/blob/main/Book-3Spark%20-%20The%20Definitive%20Guide%20-%20Big%20data%20processing%20made%20simple.pdf), so there are three main components to a Spark based architecture. A driver, cluster manager and the executors

The driver is the main component of the architecture whereas the cluster manager is what translates and maps the code taken in from the driver to its rightful executor node. It does so as if mapping a value to a location. Refer to the following sub-points:

- **Driver Program**:
	- Represents the main control process for the spark application
	- Converts user code into tasks and schedules them for execution
	- Retains information about Sparks application state
- **Cluster Manager**:
	- Manages how resources are allocated in the cluster
	- Provides access to resources for Spark applications
	- E.g.  Kubernetes, Yarn, Mesos
- **Executors**:
	- Run on worker nodes in the cluster
	- Execute tasks specified by the cluster manager
	- Store data for in-memory processing and caching

So, the typical workflow for a Spark application starts with:

1. The user submitting a task into the cluster
2. The driver program separates the inputted task into multiple sub-tasks, each with a weight based on the number of transformations and actions
3. Tasks are organized based on their data shuffling requirements (more shuffles, higher the priority)
4. Executors run the tasks based on the worker nodes
5. The results produced by these executor nodes are sent back to the driver program

The data uploaded and utilized in Spark can be retained given its in-memory processing and caching feature. Some key concepts to keep in mind about Spark include:

- **RDD** - Resilient Distributed Dataset, immutable distributed collection of data and objects that can be used to distribute the data from it while using it for lineage reconstruction in the event of their being a loss of processed data
- **DAG's** - Represents the sequence of computational tasks to be carried out