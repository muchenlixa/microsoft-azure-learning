## Introduction

Some typical examples of streaming data workloads include:

- Online stores analyzing real-time clickstream data to provide product recommendations to consumers as they browse the website.
- Manufacturing facilities using telemetry data from IoT sensors to remotely monitor high-value assets.
- Credit card transactions from point-of-sale systems being scrutinized in real-time to detect and prevent potentially fraudulent activities.

## Data Streams

A data stream consists of a perpetual series of data, typically related to specific point-in-time events. For example, a stream of data might contain details of messages submitted to a social media micro-blogging site, or a series of environmental measurements recorded by an internet-connected weather sensor. Streaming data analytics is most often used to better understand change over time. For example, a marketing organization may perform sentiment analysis on social media messages to see if an advertising campaign results in more positive comments about the company or its products, or an agricultural business might monitor trends in temperature and rainfall to optimize irrigation and crop harvesting.

Common goals for stream analytics include

- Continuously analyzing data to report issues or trends.
- Understanding component or system behavior under various conditions to help plan future enhancements.
- Triggering specific actions or alerts when certain events occur or thresholds are exceeded.

## Event Processing

### Inputs
Azure Stream Analytics can ingest data from the following kinds of input:

- Azure Event Hubs
- Azure IoT Hub
- Azure Blob storage
- Azure Data Lake Storage Gen2

Inputs are generally used to reference a source of streaming data, which is processed as new event records are added. Additionally, you can define reference inputs that are used to ingest static data to augment the real-time event stream data. For example, you could ingest a stream of real-time weather observation data that includes a unique ID for each weather station, and augment that data with a static reference input that matches the weather station ID to a more meaningful name.

### Outputs
Outputs are destinations to which the results of stream processing are sent. Azure Stream Analytics supports a wide range of outputs, which can be used to:

- Persist the results of stream processing for further analysis; for example by loading them into a data lake or data warehouse.
- Display a real-time visualization of the data stream; for example by appending data to a dataset in Microsoft Power BI.
- Generate filtered or summarized events for downstream processing; for example by writing the results of stream processing to an event hub.

### Queries
The stream processing logic is encapsulated in a query. Queries are defined using SQL statements that SELECT data fields FROM one or more inputs, filter or aggregate the data, and write the results INTO an output. 

The field used as a timestamp is important when aggregating data over temporal windows, which is discussed next.

