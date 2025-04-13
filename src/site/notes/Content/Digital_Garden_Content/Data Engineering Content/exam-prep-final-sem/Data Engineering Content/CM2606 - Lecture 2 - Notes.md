---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-2-notes/","updated":"2025-04-13T16:40:44.371+05:30"}
---

#CM2606 

## What is data modelling?

>[!Definition]
>Refers to the process of modelling a visual representation of how data elements are to be interconnected with each other such that their relationships are displayed. This includes storage, and methods in which the model may be accessed

The purpose of data modelling is to develop meaningful relationships amongst data notes within a system, displaying how data is to be structured logically and consistently. Data requirements for a business are pointed out here as well. Refer to the following points to understand the importance of data modelling:

- **Aligning with business needs** - reveals the needs of a business through essential data
- **Enhancing Data Quality** - important for identifying and rectifying inconsistencies and errors in the inputted data while enforcing rules and constraints (e.g. constraint specifying relationship types)
- **Optimizing Data Storage** - minimizes redundant data by overlaying existing columns or rows such that less space is taken, etc
- **Facilitating Data Integration** - ensures sharing and collaboration on systems through the introduction of concurrent access and role based accessed, etc
- **Supports Data Analysis** - through the introduction of a model, data analytics may be introduced to provide detailed reports in a businesses workflow

There are multiple steps to consider in data modelling:

1. **Conceptual Modelling** - Important step for identifying entities, relationships and attributes for entities while being independant of any technical aspects
2. **Logical Modelling** - Entities, attributes and relationships are defined in more detail here by specifying them in more technical (database related) terms
3. **Physical Modelling** - Defining the components required to implementing the logical model through the use of hardware components, etc

Some of the most common modelling techniques include:

- **Entity Relationship Diagrams** - Visual representation of a conceptual model that represent the entities, attributes and their relationships with other entities
- **Data Dictionaries** - Detailed documentations of data elements, inclusive of descriptions defining data types, constraints, etc

## Database Types in AWS

Refer to the following table to see a detailed breakdown on the available databases in AWS:

| Database Type      | Description                                                                                                                                                                                                                                                       | Use Case                                                                                    |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Amazon RDS         | Relational Database System provided by AWS that provides detailed relationships between different entities. It is promoted as a highly available and scalable database                                                                                            | Transactional Applications (eCommerce, Banking), ERP, Business Intelligence Analytics       |
| Amazon DynamoDB    | NoSQL database with quick/fast and predictable performance given that it does not have SQL queries, hence its fast speed. Ideal for high traffic applications that need quick responses, in other words, its ideal for real time data                             | Mobile Apps, IOT devices pipelines, Distributed serverless applications and gaming backends |
| Amazon Elasticache | An in-memory database capable of caching data while providing fast and predictable performance, ideal for high speed look ups and trend based searches                                                                                                            | Web applications with cookies or caching mechanisms                                         |
| Amazon Neptune     | Database that stores and manages data as interconnected nodes, which provides a scalable and optimized interface. Ideal for social media applications given that it can find relationships between nodes and develop recommendations based on these relationships | Social Media Applications, Recommendation Engines, Fraud Detection, knowledge Graphs        |

To conclude, here are the key pointers of each database service from AWS:

- **Amazon RDS**:
	- Relational Database System
	- Shows relationships between entities (e.g. cardinalities and foreign keys)
	- Used for transactional apps and ERP tools
- **Amazon DynamoDB**:
	- NoSQL Database System
	- Quick and fast responses
	- Ideal for high traffic applications like IOT device pipelines and gaming backends
- **Amazon Elasticache**:
	- An in-memory database capable of caching temporary data
	- Ideal for websites that use cookies or applications that store temporary data
- **Amazon Neptune**:
	- A graph database that stores data as interconnected nodes
	- Ideal for social media apps due to it being capable of showing relationships
	- Ideal for fraud detection, recommendation engines and knowledge graphs 