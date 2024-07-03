## Introducation

Many organizations work with vast amounts of data from a range of locations, relational, non-relational and other storage systems. It's a bit challenge to bring order for the big data and refine it into actionable business insights.

Microsoft Azure Data Factory is a managed cloud service that you can use to create actionable business insights from unorganized data. It help manage complex hybrid extraction, transformation, and loading (ETL), extract-load-transform, and data-integration projects.

Azure Data Factory can ingest data from on-premises, multicloud, and software as service (SaaS) data sources.

## What is Azure Data Factory (ADF)

Azure Data Factory is a cloud-based ETL and data-integration service that helps you to create data-driven workflows (AKA, pipelines) to:
- orchestrate data movement
- transform data at scale

Data Analytics is the process of gathering raw data and examining it to draw conclusions from it. This can be difficult if the data is in multiple locations, such as hosted databases and on-premises locations.

![image](images\adf\adf-overview.png)

## How Azure Data Factory works

ADF is a collection of interconnected systems that combine to provide an end-to-end data analytics platform. 

### Azure Data Factory functions

#### connect and collect

Collect the required data from the appropriate data sources, which can be located in different locations in different shapes.

Use the copy activity to move data from various sources to a single centralized data store in the cloud. After you've copied the data, you use other systems to transform and analyze it. 

1. Read data from source data store
2. Perform the following tasks on the data:
    - serialization/deserialization
    - compression/decompression
    - column mapping
3. Write data to the destination data store (AKA, the *sink*)

![image](images\adf\copy-activity-overview.png)

#### transform and enrich

After copied the data to a central cloud-based location, you can process and transform the data as needed => use Azure Data Factory mapping data flows

Data flows enable you to create data transformation graphs that run on Spark (you don't need to understand Spark clusters or Spark programming)

*ADF also supports external activities to running your transformations script manually

#### CI/CD and publish

Support for CI/CD enables you to develop and deliver your ETL processes incrementally before you publish. ADF provides for CI/CD of your data pipelines by using 
- Azure DevOps
- GitHub
> Continuous integration (CI) => automatically testing each change made to your codebase as soon as possible
> Continuous delivery (CD) => follows this testing and pushes changes to a staging or production system

After ADF has refined the raw data, you can load the data into whichever analytics engine your business users can access from their business intelligence tools

#### Monitor

After you've successfully built and deployed your data-integration pipeline, it's important that you can monitor your scheduled activities and pipelines. This allows you to track success and failure rates. ADF provides support for pipeline monitoring by using one of the following: 
- Azure Monitor
- API
- PowerShell
- Azure Monitor logs
- Health panels in Azure portal

### Azure Data Factory components

|**Component**|**Description**|
|---|---|
| Pipelines| A logical grouping of activities that perform a specific unit of work. These activities together perform a task. Advantage: you can more easily manage the activities as a set instead of as individual items|
| Activities| A single processing step in a pipeline. ADF supports these three types of activity: data movement, data transformation, and control activities|
| Datasets| Represent data structures within your data stores. These point to the data that you want to use in your activities as either inputs or outputs|
| Linked services| Define the required connection information needed for ADF to connect to external resources, such as a data source. ADF use these for two purposes: to represent a data store or a compute resource|
| Data flows| Enable your data engineers to develop data transformation logic without needing to write code => run as activities within ADF pipelines that use scaled-out Apache Spark clusters|
| Integration runtimes| ADF uses the compute infrastructure to provide the following data integration capabilities across different network environments: data flow, data movement, activity dispatch, and SSIS package execution. In ADF, an integration runtime provides the bridge between the activity and linked services|

![image](images\adf\adf-concepts.png)

## When to use Azure Data Factory

1. Do you need data integration at all? 
- if your organization is small and works with limited data sources, you probably don't need a data integration service.
- if your organization works with big data, or is a traditional relational data warehousing organization, you might benefit from a data-integration solution.

2. Do you have the coding resources needed?
- if your organization lacks the necessary coding resources to create the requried activities, consider ADF

3. Do you need to work with multiple data sources?
- if your organization has a requirement to access data in multiple locations and from multiple sources, you'll need to consider a data-integration solution that provides this support.

4. Can you create, manage, and maintain separate data integration components?
- it can be extremely complex and time-consuming to create and manage your own server-bsaed data-integration solution.