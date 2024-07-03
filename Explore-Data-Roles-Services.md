## Explore Job Roles in the World of Data

There are three job roles that deal with data in most organizations:

- **Database administrators** manage databases, assigning permissions to users, storing backup copies of data and restore data in the event of a failure
    - design, implementation, maintenance, and operational aspects of on-premises and cloud-based database systems
    - responsible for the overall availability and consistent performance and optimizations of databases
    - work with stakeholders to implement policies, tools, and processes for backup and recovery plans to recover natural disaster or human-made error
    - responsible for managing the security of the data in the database, granting privileges over the data, granting or denying access to users as appropriate

- **Data engineers** manage infrastructure and processes for data integration across the organization, applying data cleaning routines, identifying data governance rules, and implementing pipelines to transfer and tranform data between systems
    - collaborates with stakeholders to design and implement data-related workloads, including data ingestion pipelines, cleansing and transformation activities, and data stores for analytical workloads
    - use a wide range of data platform technologies, including relational and non-relational databases, file stores, and data streams
    - responsible for ensuring that the privacy of data is maintained within the cloud and spanning from on-premises to the cloud data stores
    - own the management and monitoring of data pipelines to ensure that data loads perform as expected

- **Data analysts** explore and analyze data to create visualizations and charts that enable organizations to make informed decisions
    - enables businesses to maximize the value of their data assets
    - responsible for exploring data to identify trends and relationships, designing and building analytical models, and enabling advanced analytics capabilities through reports and visualizations
    - processes raw data into relevant insights based on identified business requirements to deliver relevant insights

## Identify data services

Microsoft Azure is a cloud platform that powers the applications and IT infrastructure for some of the world's largest organizations. It includes many services to support cloud solutions, including transactional and analytical data workloads.

Some of the most commonly used cloud services for data are described below.

### Azure SQL

Azure SQL is the collective name for a family of relational database solutions based on the Microsoft SQL Server database engine. Specific Azure SQL services include:

- Azure SQL Database – a fully managed platform-as-a-service (PaaS) database hosted in Azure
- Azure SQL Managed Instance – a hosted instance of SQL Server with automated maintenance, which allows more flexible configuration than Azure SQL DB but with more administrative responsibility for the owner.
- Azure SQL VM – a virtual machine with an installation of SQL Server, allowing maximum configurability with full management responsibility.

### Azure Database for open-source relational database

Azure includes managed services for popular open-source relational database systems, including:

- Azure Database for MySQL - a simple-to-use open-source database management system that is commonly used in Linux, Apache, MySQL, and PHP (LAMP) stack apps.
- Azure Database for MariaDB - a newer database management system, created by the original developers of MySQL. The database engine has since been rewritten and optimized to improve performance. MariaDB offers compatibility with Oracle Database (another popular commercial database management system).
- Azure Database for PostgreSQL - a hybrid relational-object database. You can store data in relational tables, but a PostgreSQL database also enables you to store custom data types, with their own non-relational properties.

### Azure Cosmos DB

Azure Cosmos DB is a global-scale non-relational (NoSQL) database system that supports multiple application programming interfaces (APIs), enabling you to store and manage data as JSON documents, key-value pairs, column-families, and graphs.

### Azure Storage

Azure Storage is a core Azure service that enables you to store data in:

- Blob containers - scalable, cost-effective storage for binary files.
- File shares - network file shares such as you typically find in corporate networks.
- Tables - key-value storage for applications that need to read and write data values quickly.

### Azure Data Factory

Azure Data Factory is an Azure service that enables you to define and schedule data pipelines to transfer and transform data. You can integrate your pipelines with other Azure services, enabling you to ingest data from cloud data stores, process the data using cloud-based compute, and persist the results in another data store.

Azure Data Factory is used by data engineers to build extract, transform, and load (ETL) solutions that populate analytical data stores with data from transactional systems across the organization.

### Azure Synapse Analytics

Azure Synapse Analytics is a comprehensive, unified Platform-as-a-Service (PaaS) solution for data analytics that provides a single service interface for multiple analytical capabilities, including:

- Pipelines - based on the same technology as Azure Data Factory.
- SQL - a highly scalable SQL database engine, optimized for data warehouse workloads.
Apache Spark - an open-source distributed data processing system that supports multiple programming languages and APIs, including Java, Scala, Python, and SQL.
- Azure Synapse Data Explorer - a high-performance data analytics solution that is optimized for real-time querying of log and telemetry data using Kusto Query Language (KQL).

Data engineers can use Azure Synapse Analytics to create a unified data analytics solution that combines data ingestion pipelines, data warehouse storage, and data lake storage through a single service.

Data analysts can use SQL and Spark pools through interactive notebooks to explore and analyze data, and take advantage of integration with services such as Azure Machine Learning and Microsoft Power BI to create data models and extract insights from the data.

### Azure Databricks

Azure Databricks is an Azure-integrated version of the popular Databricks platform, which combines the Apache Spark data processing platform with SQL database semantics and an integrated management interface to enable large-scale data analytics.

Data engineers can use existing Databricks and Spark skills to create analytical data stores in Azure Databricks.

Data Analysts can use the native notebook support in Azure Databricks to query and visualize data in an easy to use web-based interface.

### Azure HDInsight

Azure HDInsight is an Azure service that provides Azure-hosted clusters for popular Apache open-source big data processing technologies, including:

- Apache Spark - a distributed data processing system that supports multiple programming languages and APIs, including Java, Scala, Python, and SQL.
- Apache Hadoop - a distributed system that uses MapReduce jobs to process large volumes of data efficiently across multiple cluster nodes. MapReduce jobs can be written in Java or abstracted by interfaces such as Apache Hive - a SQL-based API that runs on Hadoop.
- Apache HBase - an open-source system for large-scale NoSQL data storage and querying.
- Apache Kafka - a message broker for data stream processing.

Data engineers can use Azure HDInsight to support big data analytics workloads that depend on multiple open-source technologies.

### Azure Stream Analytics

Azure Stream Analytics is a real-time stream processing engine that captures a stream of data from an input, applies a query to extract and manipulate data from the input stream, and writes the results to an output for analysis or further processing.

Data engineers can incorporate Azure Stream Analytics into data analytics architectures that capture streaming data for ingestion into an analytical data store or for real-time visualization.

### Azure Data Explorer

Azure Data Explorer is a standalone service that offers the same high-performance querying of log and telemetry data as the Azure Synapse Data Explorer runtime in Azure Synapse Analytics.

Data analysts can use Azure Data Explorer to query and analyze data that includes a timestamp attribute, such as is typically found in log files and Internet-of-things (IoT) telemetry data.

### Microsoft Purview

Microsoft Purview provides a solution for enterprise-wide data governance and discoverability. You can use Microsoft Purview to create a map of your data and track data lineage across multiple data sources and systems, enabling you to find trustworthy data for analysis and reporting.

Data engineers can use Microsoft Purview to enforce data governance across the enterprise and ensure the integrity of data used to support analytical workloads.

### Microsoft Fabric

 Microsoft Fabric is a unified Software-as-a-Service (SaaS) analytics platform based on open and governed lakehouse that includes functionality to support:

- Data ingestion and ETL
- Data lakehouse analytics
- Data warehouse analytics
- Data Science and machine learning
- Realtime analytics
- Data visualization
- Data governance and management