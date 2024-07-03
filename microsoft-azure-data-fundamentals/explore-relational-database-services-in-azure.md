## Explore relational database services in Azure

### Azure SQL services and capabilities

Azure supports multiple database services, so that popular relational database management systems can be run in the cloud. 

Azure SQL is a collective term for a family of Microsoft SQL Server based database services in Azure:
- SQL server on Azure Virtual Machines (VMs) - a virtual machine running in Azure with an installation of SQL server (IaaS)
- Azure SQL managed Instance - a plateform that provides near 100% compatibility with on-premise SQL Server instances while abstracting the underlying hardawre and OS (PaaS)
- Azure SQL database - a fully managed, highly scalable PaaS datbase that designed for the cloud
- Azure SQL Edge - a SQL engine that is optimized for Internet-of-things (IoT) scenarios that need to work with streaming time-series data

### SQL server ib Azure VMs

SQL server on VMs enable you to use full version of SQL Server in the Cloud without having to manage any on-premises hardware. (IaaS approach)
- replicates the database running on real on-premise hardware
- no difference than moving database from one on-premises server to another
- suitable for migrations and applications requiring access to OS features that might be unsupported at the PaaS level. 
- create rapid development and test without buying on-premise SQL Server hardware
- lift-and-shift ready for existing applications => fast migration to the cloud with minimal changes or no changes
- scale up the platform on which SQL Server is running by allocating more memory, CPU power, disk space to the VMs

### Azure SQL Database Managed Instance

Azure SQL Managed instance runs a fully controllable instance of SQL Server in the coloud. (PaaS approach)
- Complete control over this instance as much as you would for an on-premises server
- SQL Managed Instance automates backups, software patching, database monitoring, and other general tasks
- Offers features not available in Azure SQL database, example: if you systems use features such as linked servers, service broker, database mail
- lift-and-shift an on-premises SQL server instance to the cloud without management overhead of running SQL Server on VMs
- system admin can spend less time on admin tasks as these admin tasks can be automated by the managed instance

### Azure SQL Database

PaaS offred by Microsoft => you create a managed database server in the cloud and then deploy your databases on this server.
- Microsoft manages the server so all you need to do is configure the database, create your tables and populate data. 
- single database:
    - you can scale the database if you need more storage space, memory, or processing power
    - resources are pre-allocated, you're charged per hour for the resource you've requested
- elastic pool:
    - multiple databases can share the same resources, such as memory, data storage space, processing power 
    - you create the pool and your database can use the resources from the pool
    - useful if you have databases with resource requirements that vary overtime, allocate resource when you needed and release resource once processing has completed
- best option for low cost within minimal administration (might not fully compatible with on-premises SQL server installations)
- automatically updates, patches the SQL Server software
- supports point in time restore, enable you to recover a database to the state it was in at any point in the past

### Azure for open-source database

MySQL -> leading open source relational database for Linux
- community edition => free of charge
- standard edition => higher performance, different technology for storing data
- enterprise edition => comprehensive set of tools and features: enhanced security, availability, and scalability
- Azure database for MySQL (PaaS implementation of MySQL in the Azure cloud):
    - pay for waht you use
    - automatic backups, point-in-time restore
    - connection security, firewall rules, SSL connections
    - provides a global databse system that scales up to large databases without the need to manage hardware, network components, virtual servers, software patches, etc
    - concerned with security and administration 

MariaDB -> developped by original developers of MySQL
- database engine has been rewritten and optimized for improved performance
- compatibility with Oracle Database
- built-in support for temporal data: a table can hold several versions of data, enableing an application to query the data as it appeared at some point in the past
- Azure database for MariaDB (implementation of the MariaDB database management system adapted to run in Azure):
    - fully managed by Azure, the system requires almost no additional administration

PostgreSQL -> query language called pgsql
- enable you to write stored procedures that run inside the database
- Azure database for PostgreSQL (PaaS implementation of PostgreSQL in the Azure cloud, same avilability, performance, scalingm security and admin as MySQL service)
    - some extensions might not available, example, writing stored procedures in various programming languages (other than pgsql) and interacting directly with OS
    - records information about the queries run against databases on the server