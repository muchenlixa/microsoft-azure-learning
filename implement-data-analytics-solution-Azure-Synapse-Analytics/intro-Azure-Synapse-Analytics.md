## What is Azure Synapse Analytics

Four common types of analytical technique that organizations commonly used:

- descriptive analytics: what is happening in my business? The data to answer this is typically ansered through the creation of a data warehouse, in which historical data is persisted in relational tables for multidimensional modeling and reporting.
- diagnostic analytics: why is it happening? This involve exploring information that already exists in a data warehouse, but typically involves a wider search of your data estate to find more data to support this type of analysis.
- predictive analytics: what is likely to happen in the future based on previous trends and patterns?
- prescriptive analytics: autonomous decision making based on real-time or near real-time analysis of data, using predictive analytics.

Azure Synapse Analytics provides a cloud platform for all of these analytical workloads through support for multiple data storage, processing, and analysis technologies in a single, integrated solution. The integrated design of Azure Synapse Analytics enables organizations to leverage investments and skills in multiple commonly used data technologies, including SQL, Apache Spark, and others; while providing a centrally managed service and a single, consistent user interface. 

## How it works

Azure Synapse Analytics combines a centralized service for data storage and processing with an extensible architecture through which linked services enable you to integrate commonly used data stores, processing platforms, and visualization tools. 

### Creating and using workspace

A Synapse Analyticss workspace defines an intance of the Synapse Analytics service in which you can manage the services and data resourcecs needed for your analytics solution. You can create a Synapse Analytics workspace in an Azure subscription interactively by using the Azure portal, or you can automate deployment by using Azure PowerShell, the Azure command-line interface (CLI), or with an Azure Resource Manager or Bicep template. 

### Working with files in a data lake

One of the core resources in a Synapse Analytics workspace is a data lake, in which data files can be stored an processed at scale. A workspace typically has a default data lake, which is implemented as a linked service to an Azure Data Lake Storage Gen2 container. 

### Ingesting and transforming data with pipelines

In most enterprise data analytics solutions, data is extracted from multiple operational sources and transferred to a central data lake or data warehouse for analytics. Azure Synapse Analytics includes built-in support for creating, running, and managing pipelines that orchestrate the activities necessary to retrieve data from a range of sources, transform the data as required, and load the resulting transformed data into an analytical store. 

*pipelines in Azure Synapse Analytics are based on the same underlying technology as Azure Data Factory

### Querying and manipulating data with SQL

Azure Synapse Analytics supports SQL-based querying and manipulation via two kinds of SQL pool that are based on the SQL Server relational database engine:
- a built-in serverless pool => optimized for using relational SQL semantics to query file-based data in a data lake
- custom dedicated SQL pool => host relational data warehouses

The Azure Synapse SQL system uses a distributed query processing model to *parallelize* SQL operations, resulting in a highly scalable solution for relational data processing.

### Processing and analyzing data with Apache Spark

Apache Spark is an open source platform for big data analytics. Spark performs distributed processing of files in a data lake by running jobs that can be implemented using any of a range of supported programming lanaguages, such as Python, Scala, Java, SQL and C#.

In Azure Synapse Analytics, you can create one or more Spark pools and use interactive notebooks to combine code and notes as you build solutions for data analytics, machine learning, and data visualization. 

### Exploring data with Data Explorer

Synapse Data Explorer is a data processing engine in Azure Synapse Analytics that is based on the Azure Data Explorer service. Data Explorer uses an intuitive query syntax named Kusto Query Language (KQL) to enable high performance, low-latency analysis of batch and streaming data. 

## When to use

### Large-scale data warehousing

when there's need to integrate all data, including big data, to reason over data for analytics and reporting purposes from a descriptive analytics perspective, independent of its location or structure. 

### Advanced analytics
Enables organizations to perform perform predictive analytics using both the native features of Azure Synapse Analytics, and integrating with other technologies such as Azure Machine Learning.

### Data exploration and discovery
The serverless SQL pool functionality provided by Azure Synapse Analytics enable users to explore the data within your data estate. This capability supports data discovery, diagnostic analytics, and exploratory data analysis. 

### Real time analytics
Azure Synapse Analytics can capture, store and analyze data in real-time or near-real time with features such as Azure Synapse Link, or through the integration of services such as Azure Stream Analytics and Azure Data Explorer. 

### Data integration
Azure Synapse Pipelines enables you to ingest, prepare, model and serve the data to be used by downstream systems. This can be used by components of Azure Synapse Analytics exclusively. 

### Integrated analytics
With the variety of analtyics that can be performed on the data at your disposal, putting together the services in a cohesive solution can be a complex operation. Azure Synapse Analytics removes this complexity by integrating analytics landscape into one service. That way you can spend more time working with the data to bring business benefit, than spending much of your time provisining and maintaining multiple systems to achieve the same outcomes. 