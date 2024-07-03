## Introduction

ADF provides an array of tools that enables you to transform and cleanse data to your business requirements. Many common transformation tasks can be performed code free, using the Mapping Data Flow task. You can also make use of other Azure Data Services to perform the work, and even make use of existing SQL Server Integration Packages that you have. ADF also enables you to do data exploration using Wrangling Data Flows.

## ADF Transformation Methods

Just as ADF provides a variety of methods for ingesting data, it also provides a range of methods to perform transformations. 

### Transformation with Mapping Data Flow

Mapping Data Flows provide an environment for building a wide range of data transformations visually without the need to use code. The resulting data flows that are created are subsequentyly executed on scaled-out Apache Spark clusters that are automatically provisioned when you execute the Mapping Data Flow. 

### Transformation with Compute Resources

ADF can call on compute resources to transform data by a data platform service that may be better suited the job. Example: 1. ADF can create a pipeline to an analytical data platform such as Spark pools in Azure Synapse Analytics instance to perform a complex calculation using python. 2. Send data to an Azure SQL Database instance to execute a stored procedure using T-SQL. 

### Transformation with SQL Server Integration Services (SSIS) Packages

ADF provides ability to life and shift existing SSIS workload by creating an Azure-SSIS Integration Runtime to natively execute SSIS packages. 

## ADF Transformation Types

|Category Name|Description|Example|
|---|---|---|
|Schema modifier transformations| These types of transformations will make a modification to a sink destination by creating new columns based on the action of the transformation.| The Derived Column transformation that will create a new column based on the operations performed on existing column.|
|Row modifier transformations| These types of transformations impact how the rows are presented in the destination.|Sort transformation that orders the data.|
|Multiple inputs/outputs transformations| These types of transformations will generate new data pipelines or merge pipelines into one.| The Union transformation that combines multiple data streams.|

### Data Flow Expression Buillder

Some of the transformations that you can define have a Data Flow Expression Builder that will enable you to customize the functionality of transformation using columns, fields, variables, parameters, functions from your data flow in these boxes. 