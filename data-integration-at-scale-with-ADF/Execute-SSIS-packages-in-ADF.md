## SQL Server integration services

SQL Server Integration Services (SSIS) is a platform for building complext ETL solutions. SSIS is a component within SQL Server and consists of a Windows service that manages the execution of ETL workflows, along with several tools and components for developing those workflows. It typically used to develop data integration pipelines for on-premises data warehousing solutions. It can also be used to create data migration pipelines when migrating data between different systems.

SSIS is primaryily a control flow engin that manages the execution of workflows. Workflows are held in packages, which can be executed on demand, or on a schedule. 

### SSIS projects

From SQL Server 2012, a project is the unit of deployment for SSIS solutions. You can define project-level parameters to enable users to specify run-time settings, and project-level connection managers that reference data sources and destinations used in package data flows. You can then deploy projects to an SSIS catalog in a SQL Server instance, and configure project-level parameter values and connections as appropriate for execution environments. 

### SSIS packages

A project contains one or more packages, each defining a workflow of tasks to be executed. The workflow of tasks in a package is referred to as its control flow. A package control flow can include one or more Data Flow task, each of which encapsulates its own data flow pipeline. Packages can include package-level parameters so that dynamic values can be passed to the package at run time. In previous releases of SSIS, deployment was managed at the package level.

## Understand Azure SSIS Integration Runtime

### Integration Runtime

In ADF, 
- An activity defines the action to be performed
- A linked service defines a target data store or a compute service
- An Integration Runtime (IR) provides the bridge between the Activity and Linked Services

### Azure-SSIS Integration Runtime

To lift and shift existing SSIS workloads, you can create an Azure-SSIS IR to natively execute SSIS packages for the ETL workflows.

- The location of your Azure-SSIS IR does not need to be the same as the location of your data factory, but it should be the same as the location of your own Azure SQL Database or Azure SQL Database managed instance server where SSISDB is to be hosted. This way, your Azure-SSIS Integration Runtime can easily access SSISDB without incurring excessive traffic between different locations.
- If you do not have an existing Azure SQL Database or Azure SQL Database managed instance server to host SSISDB, but you have on-premises data sources/destinations, you should create a new Azure SQL Database or Azure SQL Database managed instance server in the same location as the virtual network connected to your on-premises network. This way, you can create your Azure-SSIS IR using the new Azure SQL Database or Azure SQL Database managed instance server and joining that virtual network, all in the same location, effectively minimizing data movements across different locations.
- If the location of your existing Azure SQL Database or Azure SQL Database managed instance server where SSISDB is hosted is not the same as the location of the virtual network connected to your on-premises network, first create your Azure-SSIS IR using an existing Azure SQL Database or Azure SQL Database managed instance server and joining another virtual network in the same location, and then configure a virtual network to virtual network connection between different locations.