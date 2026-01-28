---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-8-notes/","updated":"2025-04-16T19:53:57.534+05:30"}
---

#CM2606

## Data Pipelines

>[!Definition]
>A data pipeline is simply a stream of data that flows in from a source to a point where it is processed and then loaded onto another location

The simplest form of a pipeline is where data is collected from an origin and then processed/transformed and then loaded into a destination. 

![[Pasted image 20250416190639.png\|Pasted image 20250416190639.png]]

In some occasions, the collected data would need to be stored in a "staging" area for further processing like so:

![Pasted image 20250416190718.png](/img/user/pngs/Pasted%20image%2020250416190718.png)

The components of the diagram are like so:

- **Origin** - Source of where all the data is collected from, can be database, API, etc
- **Destination** -The termination point of the data flow where is is the point that the data was/is meant to be delivered
- **Staging** - A place where the data is persisted in different stages and processed and passed onto the next stage
- **Processing** - Refers to making changes to the data before and after it is moved into a staging area:
	- **Transforming Before Staging Data** - Cleaning, filtering and sanitizing the data to ensure that it is fit to be processed safely 
	- **Transforming After Staging Data** - Partition and catalogue the data to categorize it for the next stage or destination so it can be used easily
- **Dataflow** - Refers to the flow of data through the entire process from origin to destination

In some cases, the data does not need to be processed rather it can directly be fed into the systems destination (e.g. data warehouse):

![Pasted image 20250416191341.png](/img/user/pngs/Pasted%20image%2020250416191341.png)

In other occasions the data can be processed and transformed and then sent back to the same source (origin):

![Pasted image 20250416191400.png](/img/user/pngs/Pasted%20image%2020250416191400.png)

A typical data pipeline is similar to the following:

![Pasted image 20250416191447.png](/img/user/pngs/Pasted%20image%2020250416191447.png)

The components of the data pipeline mentioned above can be broken down like so:

| Component   | Description                                                                                                                                                                             | Example                                                                                                                                                                                                                                         |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Data Source | Source of where the data comes from which could be anything from transactional data to surveillance data                                                                                | Transactional Data (e.g. data from POS or ATM systems), Databases, Clickstream data (e.g. data generated from web applications), Logs (historical data from interactions made on web application), Social Media, Sensor Data, Surveillance data |
| Ingestion   | Refers to the process of how the data is collected from each source which could be anything from a single push to a repository to a complex collection from multiple sources            | Push to a system, Pull from a system, Data Streaming                                                                                                                                                                                            |
| Data Lake   | A landing zone for raw data collected from each source that is transformed to a minimal extent or not at all and is stored in multiple formats. It is partitioned by the data collected | Conversions that may occur in a lake: CSV to xlsx or similar domains                                                                                                                                                                            |
The main features of an AWS pipeline include seamless integration with other services such as CloudWatch for monitoring or S3 for offloading into. The services are scalable and very flexible.

## What are workflow management systems?

>[!Definition]
>Basically a system that helps you monitor and manage your data pipelines by automating or scheduling tasks, coordinating load locations and orchestrating other processes to occur if another does

Some of the key benefits of using a workflow management system (WMS) include:

- **Centralized Control** - Everything is in one place and easily manageable, providing a holistic view of the entire process, hence simplifying the entire operation
- **Visual Workflow Creation** - Easy to drag and drop processes now (e.g. Airflow)
- **Scheduling and Triggering** - Events can occur at scheduled times or can be programmed to be triggered when an event occurs, hence the importance of a WMS
- **Error Handling and Recovery** - Easy to setup mitigation plans when errors occur or to simply set alerts that are prompted in the case of an error occurring. Recovery methods are introduced as well with caching, etc
- **Scalable and Resilient** - Can handle increasing volumes and loads of data to maximize and optimize higher velocity data intakes

Some AWS WMS options include:

- **AWS Step Functions** - Serverless workflow service with visual workflow creation
- **AWS Glue** - Integration service that includes scheduling services and ETL job creations with a visual interface
- **Amazon Managed Workflows for Apache Airflow (MWAA)** - Solution service that offers pre-set deployments of Airflow onto AWS services in a scalable manner

When it comes to deciding on what WMS is optimal for a given use case, consider the following features:

- Data volume and pipeline complexity
- Ease of use
- Interpretability from existing tools and services for integrations
- Scalability and cost

To conclude, the integration of a WMS in a data pipeline helps orchestrate everything with ease while optimizing workflows and improving operational efficiency.

## What is MLOps?

>[!Definition]
>Refers to the process of orchestrating and optimizing machine learning lifecycles through similar concepts that a devops engineer would implement. It in other words, is a set of practices carried out to streamline and automate the end to end process of a machine learning lifecycle 

The end goal of an MLOps engineer is to ensure that a machine learning model functions properly in production and ensures reliability and efficiency. The key components of a MLOps engineer include:

- Data Management
- Model Development 
- Model Deployment (e.g. Containerization through Docker, etc)
- Monitoring pipelines and performances (inclusive of model retraining if the model were to be outdated)
- Collaboration through tools like Jira

Some tools and technologies utilized in the process include:

- Data versioning through tools such as Delta Lake
- Experiment tracking
- Model Deployment through containers (e.g. Docker, Kubernetes, Tensorflow)
- Monitoring (e.g. Prometheus, Grafana) 
- Continuous Integration/Continuous Delivery (CI/CD) - GitHib, Jenkins

Some best practices an MLOps engineer can follow include:

- Data versioning 
- Pipeline automation with scheduling, etc
- Continuous Monitoring 
- Efficient Collaboration
- Documenting everything 