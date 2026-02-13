---
{"dg-publish":true,"permalink":"/content/digital-garden-content/airflow-astronomer-certification/content/introduction-topics/running-airflow/","updated":"2026-02-12T11:08:38.267+05:30"}
---

#Astronomer #Airflow 

## How can you run airflow?

>[!Important]
>Before you can actually get into running airflow you first need to figure out how large the size of your team is to be when you work in a project and it may be broken down into the following categories.

In terms of how the complexity evolves over time it tends to scale up due to the increase in requirement for the number of persons working on the project due to how it increments the number of DAG's, tasks and deployments.

- **Developers** - ideal for persons simply learning and experimenting with airflow with the ideal of working with only a single developer. Besides that the setup and cost is expected to be simple to setup and cheap to maintain. You can expect to set it up locally through docker in most instances.
	- You can expect to run these on a local machine or VM
	- These are normally on-premises, meaning that it will not be run on the cloud unless it was considered

- **Single Teams** - Intended for production with multiple developers which is inclusive of single to multiple deployments. It is required to be highly available, multi-tenant as well as very scalable.
	- Can be run on virtual machines or deployed environment like AWS EKS, EC2 instance, etc
	- Could be on prem or off prem based on the regulations and rules to be adhered to
	- Expected to be scalable and easy to expand (cost begins to deter here)

- **Multi Teams** - This is where airflow is scaled into a large space as to where it is intended for production, multiple teams of developers, and multiple deployments. However, in this instance, Airflow is intended to be very customizable, highly available and multi tenant.
	- Given there are multiple teams, this will have strict rules and regulations to adhere to.
	- May run on fully managed airflow services such as astro, etc