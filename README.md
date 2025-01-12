# Earthquake data pipeline using Microsoft Fabric

## Objective
The objective of this project is to get hand-on exposure of Microsoft Fabric.
It's a starting point before diving deeper into the Microsoft world.

## Setting up
This project will be done in the Microsoft Fabric environment.
If you're new to it like me, what is Fabric ?

Fabric offers a 60-day free trial, so let's create an account :
https://www.microsoft.com/en-us/microsoft-fabric/getting-started

![Architecture diagram](images/architecture_diagram.png)
Fabric offers the following solutions :
- Power BI: lets you easily connect to your data sources, visualize, and discover what's important, and share that with anyone or everyone you want.

- Data Factory: provides a modern data integration experience to ingest, prepare, and transform data from a rich set of data sources.

- Industry Solutions: industry-specific data solutions that address unique industry needs and challenges, and include data management, analytics, and decision-making.

- Real-Time Intelligence: an end-to-end solution for event-driven scenarios, streaming data, and data logs.

- Data Engineering: provides a Spark platform with great authoring experiences. It enables you to create, manage, and optimize infrastructures for collecting, storing, processing, and analyzing vast data volumes.

- Data Science: enables you to build, deploy, and operationalize machine learning models from Fabric.

- Data Warehouse: provides industry leading SQL performance and scale. It separates compute from storage, enabling independent scaling of both components.

## Architecture
Now that we have an overall idea about the components of Microsoft Fabric, here are the components that will be useful for this project : 

### Data Source
I will be using the USGS Earthquake data for this project, extracting it through an API using Python and Spark.

### Data Engineering
I will then incrementally process the data using the medallion architecture, which is a design pattern used to logically organise data in a lake house, with the goal of progressively improving the structure and quality of data as it flows through each layer :
- Bronze : data in its raw form, largely unchanged from the source
- Silver : involves cleansing and transforming the data, making corrections and consolidations as needed 
- Gold : where the most refined and business ready data resides, optimized for high value actionable insights, often tailored for specific business needs

All of this will be done using Synapse Data Engineering.

### Data Orchestration
Once the Data Engineering notebooks are created, I will use Data Factory to orchestrate and automate them to ingest and append the data to the bronze, silver and gold layers on daily basis.


### Data Analysis and reporting
I will create a Power BI report to show the worldwide earthquake data events.

![Architecture diagram](images/architecture_diagram.png) 
_Diagram created using [Excalidraw]
