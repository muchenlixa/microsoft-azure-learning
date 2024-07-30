## Stream ingestion scenarios

Azure Synapse Analytics provides multiple ways to analyze large volumnes of data. Two of the most common approaches to large-scale data analytics are:
- Data warehouses - relational database, optimized for distributed storage and query processing. Data is stored in tables and queried using SQL
- Data lakes - distributed file storage in which data is stored as files that can be processed and queried using multiple runtimes, including Apache Spark and SQL

### Data warehouses in Azure Synapse Analytics

It provides dedicated SQL pools that you can use to implement enterprise-scale relational data warehouse. Dedicated SQL pools are based on a massively parallel processing (MPP) instance of the Microsoft SQL Server relational database engine in which data is stored and queried in tables. 

### Data lakes in Azure Synapse Analytics

An Azure Synapse Analytics workspace typically includes at least one storage service that is used as a data lake. Most commonly, the data lake is hosted in an Azure Storage account using a container configured to support Azure Data Lake Storage Gen2. Files in the data lake are organized hierarchically in directories (folders), and can be stored in multiple file formats, including delimited text (such as comma-separated values, or CSV), Parquet, and JSON.

## Configure inputs and outputs

All Azure Stream Analytics jobs include at least one input and output. In most cases, inputs reference sources of streaming data (you can also define inputs for static reference data to augment the streamed event data). Outputs determine where the results of the stream processing query will be sent. In the case of data ingestion into Azure Synapse Analytics, the output usually references an Azure Data Lake Storage Gen2 container or a table in a dedicated SQL pool database.

### Streaming data inputs
- Azure Event Hubs
- Azure IoT Hubs
- Azure Blob or Data Lake Gen2 Storage

### Azure Synapse Analytics outputs
If you need to load the results of your stream processing into a table in a dedicated SQL pool, use an Azure Synapse Analytics output. 

### Azure Data Lake Storage Gen2 outputs
If you need to write the results of stream processing to an Azure Data Lake Storage Gen2 container that hosts a data lake in an Azure Synapse Analytics workspace, use a Blob storage/ADLS Gen2 output. 