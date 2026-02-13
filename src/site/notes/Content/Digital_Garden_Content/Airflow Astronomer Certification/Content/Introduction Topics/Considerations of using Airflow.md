---
{"dg-publish":true,"permalink":"/content/digital-garden-content/airflow-astronomer-certification/content/introduction-topics/considerations-of-using-airflow/","updated":"2026-02-11T17:51:28.697+05:30"}
---

#Airflow #Astronomer 

## What should we be aware of when using Airflow?

>[!Important]
>Keep in mind that Airflow follows a batch processing architecture where it must process everything in batches, hence why streaming data in real time is not ideal in terms of using it through airflow

Although Airflow may not be ideal for streaming data in a continuous pipeline, it may be used to schedule a task that could initiate another to carry out a streaming process, such as initiating a process in [[Content/Digital_Garden_Content/Data Engineering Content/Kafka Confluent\|Kafka Confluent]]. What may happen here is that the pipeline could trigger a streaming service to occur in continuously upload some sort of data through a real time streaming service such as kafka for real time data streaming for sensors, etc.

Some of the main use cases of airflow included:

- Streaming
- Scalability
- Data Processing

It tends to experience issues through mostly scalability when there isn't enough resources allocated to it and due to faulty infrastructures that tend to cause failures.