---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-6-notes/","updated":"2025-04-15T18:21:01.521+05:30"}
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