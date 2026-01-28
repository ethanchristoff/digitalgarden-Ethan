---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-6-notes/","updated":"2025-04-15T18:52:37.628+05:30"}
---

#CM2606 

## What is Apache Kafka?

>[!Definition]
>Kafka is a data streaming service where data can be produced onto it and consumed from another machine in another end. The data stored in it can be retained for a given period of time before expiring 

Through the use of Kafka you can implement a process known as event streaming, it refers to the process of streaming a real time event from a source onto a platform that proceeds to store it and then retain it until consumed or utilized. The stored data is not manipulated until received or retrieved by a device. 

To generalize how Kafka works:

- It's a distributed system that communicates between servers and clients
	- A **server** consists of a series of clusters of one or more servers which come together to form the storage layer, these servers that come together are called brokers
	- A **client** is simply an entity that connects/communicates with a Kafka cluster to read and write from it by producing data into it or consuming data from it
- It is deployed in a high performing TCP network which is inclusive of hardware and virtual machines 

>[!important]
>To conclude what Kafka is, its a distributed streaming service run on a cluster of servers that act as brokers and consumers for data. It holds onto the data that is produced into it for a given period of time and then sent back to a consumer, the data it stores is referred to as events

Some main terminologies to keep in mind include:

- **Broker** - Provider/server in a Kafka cluster that represents the storage layer in which data is consumed and produced into
- **Producers** - Clients that write data into a Kafka clusters are known as producers
- **Consumers** - Clients that read data from clusters are known as consumers
- **Event** - A record of something happening is referred to as an event, it could be a message document, etc. These events come with time stamps to state when it was produced and how long it will take to expire based on the data retention period
- **Topic** - Represent a common group of events that a client may produce into, hence the name topic. Anything uploaded into it either has a common attribute or is uploaded there to store it there as if it were storing data under a subfolder

When data is written into a Kafka cluster, it is partitioned into multiple servers where it may then be accessed parallelly from a single publication. **When an event is produced into a topic, its data is appended to the partition the topic is stored in**.

## Data Transformation Types

>[!Definition]
>Data transformation refers to the change of format, structure of values in data to adhere to the location it is to be stored in and the manner in which it is to be accessed.

The process normally takes place in the transformation segment of an ETL pipeline. So, there are different types of transformations that can be made to data for it to fit in a category, regard the following:

- **Constructive Transformation** - Adding, Copying, Replicating data
- **Destructive Transformation** - Deleting Fields and Records
- **Aesthetic Transformation** - Normalizing and Standardizing data to fit a category (e.g. Standardizing salutations to peoples names)
- **Structural Transformations** - Renaming, Combining column
- **Type Transformations** - Converting the data type through formatting 
- **Parsing Data** - Here you reparse data to either take up less memory or to curate it by adding commas to csv, as an example

## Cleaning Data

Now when it comes to cleaning data there are some methods to consider:

- Filtering out unnecessary values and fields 
- **Ambiguity Handling** - this refers to handling categorical variables by reusing them to avoid redundancy (e.g. T-shirt sizes can say "small" or "s", so it can be cleaned to just say "s")
- Duplication handling to remove duplicate values and corrupt data handling
- To handle missing values, rows may be dropped and ratios may be assessed to see if the column may be dropped, etc
	- Replacing values may be a viable option as well

### Scaling Data

>[!Definition]
>Scaling refers to the process of normalizing values to fit a certain range such that they are normalized and extended ranges do not need to be considered, other wise the data ranges may be standardized instead

The entire point of scaling is to limit ranges in data such that it does not exceed a limit and cause underlying issues, the following are solutions to this issue:

- **Min-Max Scaler** - Shrinks feature value to a range of choice, hence setting a custom min and max value
- **Normalization** refers to the process of scaling in respect to the entire dataset so that the data will only have a range from 1 to 0
- **Standardization** refers to the process of **transforming in respect to entire data ranges while ensuring that the data has a mean of 0 and a standard deviation of 1**, hence making its distribution a standard normal distribution. Each value differs from each other by only one unit

### Data Enrichment Techniques

>[!Definition]
>To clean the data further, columns and rows may be enriched to hold more information such that it does not have to be repeated over multiple columns, hence overlaying the redundant factor 

- **Aggregation** - Refers to creating aggregate columns that hold collective data that can define multiple other columns (e.g. total transaction count, etc)
- **Deformalizing Schemas** - Adding in other columns for the sake of better explanations
- **Merging** - Simply merging columns with each other

### Data Sanitization

>[!Definition]
>Refers to the process of sanitizing the data by simply maintaining security standards and ensuring the personally identifiable information (PII) remain safe

- **Anonymization** -Removing PII from datasets
- **Encryption** - Encrypting the data such that PII is not revealed

Take the following for example, data before sanitization:

![[Pasted image 20250415184957.png\|Pasted image 20250415184957.png]]

Data after sanitization:

![[Pasted image 20250415185019.png\|Pasted image 20250415185019.png]]
### Data Validation

>[!Definition]
>The final step to data cleaning refers to the process of validating the data to ensure accuracy and integrity.

It maybe done so by assessing if the data still adheres to the mentioned rules and constraints through:

- Range Checks
- Consistency Checks (e.g. cross referencing related fields)
- Data type validations
- Pattern Matching (e.g. checking valid email formats)
- Business rule validation (e.g. Checking to see if data adheres to business logic)