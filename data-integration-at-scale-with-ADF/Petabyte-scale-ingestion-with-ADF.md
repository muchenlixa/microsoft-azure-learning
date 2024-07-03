## Introduction

The first stage of data integration work is to ingest source data from any number of systems into a destination, or an intermediary data store. ADF offers naerly a hundred different data connectors to ingest data. Regardless of which method you choose, you must set up the appropriate infrastruture to support the data ingestion method through integration runtimes. Additionally, you must also make sure that the data ingestion is secure in each data store, and whilst in transt. 

## List the data factory ingestion methods

ADF can accommodate organizations that are embarking on data integration projects from the differing starting point. 

Typically, many data integration workflows must consider existing pipelines that have been created on previous porjects, with different dependencies and using different technologies. To that end, there are various ingestion methods that can be used to extract data from a variety of sources. 

## Ingesting data using the Copy Activity

This method offers code-free data ingestion pipelines that don't require any transformation during the extraction of the data. Suitable for any greenfield projects that have a simple method of extraction to an intermediary data store. An example of ingesting data using the Copy Activity can include extracting data from multiple source database systems and outputting the data to files in a data lake store. The benefit of this ingestion method is that they are simple to create, but they are not able to deal with sophisticated transformations or business logic. 

## Ingesting data using Compute Resources

ADF can call on compute resources to process data by a data platform service that may be better suited to the job. A great example of this is that ADF can create a pipeline to an analytical data platform such as Spark pools in an Azure Synapse Analytics instance to perform a complex calculation, which generates new data. This data is then ingested back into the pipeline for further downstream processing. 

## Ingesting data using SSIS Packages

Many organizations have SQL Server Ingegration Services (SSIS) packages from years of business operations. These packages contian both ingestion and transformation logic from on-premises and cloud data stores. ADF can lift and shift existing SSIS workload by creating an Azure-SSIS Integration Runtime to natively execute SSIS packages.

## Data Factory Connectors

Connectors = ADF objects that enable your linked services and datasets to connect to a wide variety of data sources and sinks. 

## Data Ingestion Security Considerations

Data integration requries the secure handling of data that is both at rest and in transit. Prior to the creation of a data integration solution, the design stage must consider the security requirements. 

### Network

- Use virtual netwroks to secure Azure resources
- Use services to detect and prevent intrusions
- Simplify the management of security rules using network service tags

### Identity and access control

- Administrative accounts
- Use active directory to make use of single sign-on

### Data protection

- Use Role Based Access Control (RBAC) to control access to the resources
- Sensitive data

### Logging and monitoring

- Configure central security log management
- Monitor and log the configuration and network packet traffic of virtual networks, subnets, and NICs
- Enable audit logging
- Enable alerts on activities
- Follow standard logging and monitoring standard within your organization