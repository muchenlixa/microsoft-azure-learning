## Introduction

Lare-scale data analytics combine conventional data warehouse used to support BI with data lakehouse techniques that used to integrate data from files and external sources. 

A conventional data warehousing solution typically involves copying data from transactional data stores into a relational database with a schema that's optimized for querying and building multidimensional models. 

Data lakehouse solutions on the other hand, are used with large volumnes of data in multiple formats, which is batch loded or captured in real-time streams and stored in a data lake from which distributed processing engines like Apache Spark are used to process it. 

## Data ingestion pipelines

On Azure, large-scale data ingestion is best implemented with pipelines that orchestrate ETL process. This can be achieved via either Azure Data Factory or Azure Synapse Analytics. In either case, pipelines consist of one or more activities that operate on data. An input dataset provides the source data, and activities can be defined as a data flow that incrementally manipulates the data until an output dataset is produced. Pipelines can connect to external data sources to integrate with a wide variety of data services. 

## Data stores

### Data warehouses

A data warehouse is a relational database in which the data is stored in a schema that is optimized for data analytics rather than transactional workloads. 

Commonly, the data from a transactional store is transformed into a schema in which numeric values are stored in central fact tables, which are related to one ore more dimension tables that represent entities by which the data can be aggregated. 

For example, a fact table contain sales order data, which can be aggregated by customer, product, store, and time dimensions. This kind of fact and dimension table schema is called star schema, though it's often extended into a snowflake schema by adding additional tables related to the dimension tables to represent dimensional hierarchies. 

### Data lakehouses

A data lake is a file store, usually on a distributed file system for high performance data access. Technologies like Spark or Hadoop are often used to process queries on the stored files and return data for reporting and analytics. These systems often apply a schema-on-read approach to define tabular schemas on semi-structured data files at the point where the data is read for analysis, without applying constraints when it's stored. Data lakes are great for supporting a mix of structured, semi-structured, and even unstructured data that you want to analyze without the need for schema enforcement when the data is written to the store. 

