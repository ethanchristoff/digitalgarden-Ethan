---
{"dg-publish":true,"permalink":"/content/digital-garden-content/airflow-astronomer-certification/content/introduction-topics/introduction-to-orchestration/","updated":"2026-01-26T15:43:22.641+05:30"}
---

#Astronomer #Airflow 

## What is orchestration?

>[!Important]
>It refers to the process of coordinating and automating data flows across various tools and systems to deliver quality data products and analytics. In other words, data orchestration is simply organizing a sequence of events to occur and trigger when specific events take place to control the flow of data from one (or multiple points) to another point (or again, multiple points)

In the image below there are four main stages to be considered when it comes to how data orchestration had been developed over time:

![Pasted image 20260126151021.png](/img/user/pngs/Pasted%20image%2020260126151021.png)

- **Pre-Unix Era** - Composed of manual batch processing and scheduling, hence where the concept and idea of data orchestration had started.
	- **Limitations**: 
		- Entire process was manual, hence prone to errors and had a lot of human errors. 
		- Did not have standardized approach to data standardization, formats, protocols or processing techniques.
- **Early Computing Era** - Composed of basic time based scheduling tools, dedicated ETL tooling as well as a rise in proprietary scheduling and management tools (*e.g. CRON, Autosys, Informatica*).
	- **Limitations**:
		- Proprietary software's were expensive
		- Schedulers like CRON, Windows Task Scheduler (WTL) and Informatica lacked features for more complex workflows, hence making the difficult to maintain
- **Data & Open Source Renaissance** - Period where more complex tools were developed to handle and maintain more complex tools, hence the increase in complexity, size, heavier/complex ETL (**Extract Transform & Load**) workflows and the rise in open source management projects (*e.g. Oozie, Azkaban, Luigi*).
	- **Limitations**:
		- Some tools were limited to only working in hadoop ecosystems
		- Some tools relied on using XML/Config files to define workloads
		- Not scalable, dynamic or extendable
- **Modern Data Orchestration** - In this era there was an introduction to pipelines as well as an increase in the number of possible integrations into other systems. **Time & event** based scheduling was introduced as well as a easy to understand UI (*e.g. Airflow*).

To summarize the eras, refer to the following:

- **Pre-unix era** - Made up of manual batch processing software's that were composed of multiple human errors due to tasks being done manually.
- **Early Computing Era** - Composed of basic time based scheduling tools which were mostly expensive proprietary softwares inclusive of CRON, WTS and Informatica
- **Data & Open Source Renaissance** - Period where there was a surge in data orchestration tools that had a tendency to rely on config and xml files as well as function in only hadoop based systems, hence why it was difficult to scale.
- **Modern Data Orchestration** - Period of time where conventional tools like airflow was introduced and composed of **pipelines** that had a UI to help understand how certain things occur