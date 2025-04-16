---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-8-notes/","updated":"2025-04-16T19:14:49.303+05:30"}
---

#CM2606

## Data Pipelines

>[!Definition]
>A data pipeline is simply a stream of data that flows in from a source to a point where it is processed and then loaded onto another location

The simplest form of a pipeline is where data is collected from an origin and then processed/transformed and then loaded into a destination. 

![Pasted image 20250416190639.png](/img/user/pngs/Pasted%20image%2020250416190639.png)

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

