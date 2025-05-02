---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-lecture-9-notes/","updated":"2025-04-17T14:03:01.000+05:30"}
---

#CM2606

## Why is cloud and big data important for machine learning?

Given that machine learning models get more complex at any given time due to the fact that they tend to stay up to data with trends in order to maintain a more truthful and consistent knowledge base, a storage medium for big data is required. 

Besides that, machine learning models cannot be processed locally on just any laptop given how resource intensive they are, so through the introduction of cloud computing resources the issue of processing power, etc, may be mitigated.

To summarize:

- Big data provides massive datasets
- Bigger datasets lead to more progressive and better ML predictions
- Cloud computing is cheaper and more scalable
- Offers distributed processing 

Through the combination of both cloud resources and big data processing, machine learning models are capable of being run from any place with ease.

## What are some challenges faced in ML with big data?

Some of the most common challenges include handling large volumes of data which often lead to bottlenecks and issues with time consumption in having to process the entire dataset. The metrics that define the volume of data include:

- Number of records
- Number of features and attributes
- Performance issues in processing

To conclude, the key features that poses as a challenge to machine learning include:

- Data Volume
- Velocity
- Variety (Structure, Semi-Structured and unstructured data)
- Infrastructure (the framework in which the model is to be hosted in)

## How is Apache Spark relevant to machine learning?

>[!Definition]
>Given that spark is a distributed computational engine that is capable of processing data in multiple machines concurrently or in separate threads and batches, it is ideal for machine learning models given that it can carry out resource intensive tasks related to model development with ease

Spark has an exclusive library for machine learning called `mlib`. It offers a series of features such as:

- Classification
- Regression 
- Clustering
- Recommendation (e.g. ALS for collaborative filtering)
- Feature extraction and transformation
- Pipelines for ML workflows

## What is model serving?

>[!Definition]
>It refers to the process of deploying and implementing a pre-trained model in a production environment

In the process of "serving" a model, it is trained to a standard such that it can successfully serve users through an endpoint without experiencing any technical difficulties or issues related to the model such as overfitting. Models can be served in two manners:

- **Batch Serving** - Schedule when and what data is to be fed into the model and how the response is to be taken out
- **Online Serving** - Expose the model to be consumed as required without a fear of them receiving incorrect responses

The machine learning process of deploying a model into a production level standard is like so:

![Pasted image 20250417131830.png](/img/user/pngs/Pasted%20image%2020250417131830.png)

In a cloud based ingestion flow you would need to consider the following features:

- **Data Ingestion** - Kafka, AWS kinesis
- **Data Storage** - S3, Redshift, Azure 
- **Processing** - Spark MLib, Fink, Tensorflow
- **Training** - Sagemaker (helps stage end-to-end pipelines for model re-training)
- **Deployment** - Kubernetes through docker (when they talk about deployment they usually refer to how they would containerize the application and then deploy it)

Some best practices that may be implemented to ensure efficiency and productivity include:

- **Data Partitioning** - Categorizing and segregating the data such that it isn't all processed in a single partition which could lead to errors and potential crashes
- **Model Monitoring** - Continuously monitor the model to ensure it performs up to standard
- **Cost Control** - May be maintained through AWS as it bills you as you go
- **Security** - Issue IAM roles and policies to limit access to PII or other similar features in a model such that safety is guaranteed

## What is data parallelism?

>[!Definition]
>Also known as **Distributed Data Parallelism** (DDP). It refers to how a model is replicated onto multiple devices and the dataset is separated into smaller shards and then fed into each device (with the model), parallelly to process them efficiently 

Some frameworks that may be implemented for each process include:

- Replicating the model onto multiple devices - PyTorch
- Splitting the dataset into shards - Tensorflow
- Sync each devices outcome together - Horovod

## What is model parallelism?

>[!Definition]
>Also know as **Fully Sharded Data Parallelism** (FSDP), the models architecture is split across multiple devices (not replicated). The data is not fragmented here rather it is directly fed into the system
>

The model can be separated here in two different manners:

- **Layer Wise** - (Vertical) different layers will be handled by different GPU's given how resource intensive that layer is
- **Tensor Wise** - (Horizontal) here the model is split into weight matrices

## Difference between Data Parallelism and Model Parallelism?

>[!Definition]
>The main difference between each method is that in data parallelism the data is split across multiple machines that the model has been replicated on while model parallelism is where the model has been split across machines

Another key factor to keep in mind is that data parallelism is used when the dataset is too large but the model can be run on the same hardware whereas model parallelism is when the model cannot be run on one GPU whereas it has to be distributed amongst multiple layers instead.

In model parallelism, the output of a model may be to much to process on a single GPU, so its operations may be distributed over multiple nodes instead to minimize compute times. Take the following operation for example:

$x \sqrt y$

This operation can be shared across multiple nodes to get the output as a whole in the end. Refer to the following tables to see some more features that differ from each other:

| Feature              | Data Parallelism                             | Model Parallelism                                            |
| -------------------- | -------------------------------------------- | ------------------------------------------------------------ |
| **What is split?**   | The **data** is split across devices         | The **model** (layers or operations) is split across devices |
| **Each device gets** | A **copy** of the full model                 | A **part** of the model                                      |
| **Used when...**     | The model fits in one GPU, but data is large | The model is too large for one device                        |
| **Sync needed?**     | Yes, gradients must be synchronized          | Yes, outputs must be passed between devices                  |
| **Common use case**  | Training ResNet on image batches             | Training a large transformer like GPT                        |

Now there is also a hybrid option that integrates both model and data parallelism, its known as **pipeline parallelism**. 

## What is pipeline parallelism?

>[!Definition]
>It is a hybrid model between data and model parallelism where the model may be split across multiple nodes and the data can be separated and fed into each node as well. The process follows a similar layout to a pipeline
>

Similar to a pipeline, each stage is assigned to a different device where each stage handles different batches of data as if assembling the data from the source to the output.

So to conclude:

- Data Parallelism - For when the dataset is too big
- Model Parallelism - For when the model is too complex (e.g. LLMS)
- Pipeline Parallelism - For when the entire process is complex