---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/exam-prep-final-sem/data-engineering-content/cm-2606-final-notes-and-essential-reading/","updated":"2025-04-22T23:06:04.957+05:30"}
---

#CM2606 

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