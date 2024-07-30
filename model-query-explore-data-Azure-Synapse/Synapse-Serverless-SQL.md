## Azure Synapse Serverless SQL

### Serverless SQL pools

Azure Synapse SQL is a distributed query system in Azure Synapse Analytics that offers two kinds of runtime environments:
- Serverless SQL pool: on-demand SQL query processing, primiarily used to work with data in a data lake
- Dedicated SQL pool: enterprise-scale relational database instances used to host data warehouses in which data is stored in relational tables

Benefits of using serverless SQL pool:
- familiar Transact-SQL syntax to query data without the need to copy or load data into a specialized store
- integrated connectivity from a wide range of business intelligence and ad-hoc querying tools, including the most popular drivers
- distributed query processing that is built for large-scale data, and computational functions - resulting in fast query performance
- built-in query execution fault-tolerance, resulting in high reliability and success rates even fro long-running queries involving large data sets
- no infrastructure to setup or clusters to maintain. A built-in endpoint for this service is provided within every Azure Synapse workspace, so you can start querying data as soon as the workspace is created
- No charge for resources reserved, you're only charged fro the data processed by queries you run

Azure Synapse SQL pool is tailored for querying the data residing in the data lake, so in addition to eliminating managment burden, it eliminates a need to worry about ingesting the data into the system. You just point the query to the data that's already in the lake and run it.

### Query files

You can query data files in the following formats:
- Delimited text, such as comma-separated values (CSV) files
- JavaScript object notation (JSON) files
- Parquet files

The basic syntax for querying is the same for all of thest types of file, and is built on the OPENROWSET SQL function, which generates a tabular rowset from data in one or more files. For example:
```sql
SELECT TOP 100 *
FROM OPENROWSET (
    BULK 'https://mydata.blob.core.windows.net/data/files/*.csv',
    FORMAT = 'csv') AS ROWS
```
The OPENROWSET function includes more parameters that determine factors such as:
- the schema of the resulting rowset
- additional formatting options for delimited text files

The output from OPENROWSET is a rowset to which an alias must be assigned. In the previous example, the alias rows is used to name the resulting rowset. 

The BULK parameter includes the full URL to the location in the data lake containing the data file. This can be an individual file, or a folder with wildcard expression to filter the file types that should be included. The FORMAT parameter specifies the type of data being queried. The example above reads delimited text from all .csv files in the files folder. 

You can also specify multiple file paths in the BULK parameter, separating each path with a comma.

Some additional parameters:
- PARSER_VERSION: 1.0 is the default and supports a wide range of file encodings, while 2.0 supports fewer encodings but offers better performance.
- FIRSTROW: skip rows in the text file, to eliminate any unstructured preamble text or to ignore a row containing column headings.
- FIELDTERMINATOR: the character used to separate field values in each row. For example, a tab-delimited file separates fields with a TAB (\t) character. The default terminator is a comma(,).
- ROWTERMINATOR: the character used to signify the end of a row of data. For example, a standard Windows text file uses a combination of carriage return (CR) and line feed (LF), which is indicated by the code \n; while UNIX-style text files uses a single line feed character, which can be indicated using the code 0x0a. 
- FIELDQUOTE: the character used to enclose quoted string values. For example, to ensure that the comma in the address field value 126 Main St, apt 2 isn't interpreted as a field delimiter, you might enclose the entire field value in quotation marks like this: "126 Main St, apt 2". The double-quote (") is default field quote character. 

When querying JSON files:
```sql
SELECT doc
FROM 
    OPENROWSET (
        BULK 'https://mydata.blob.core.windows.net/data/files/*.json',
        FORMAT = 'csv',
        FIELDTERMINATOR = '0x0b',
        FIELDQUOTE = '0x0b',
        ROWTERMINATOR = '0x0b'
        ) WITH (doc NVARCHAR(MAX)) AS ROWS
```

OPENROWSET has no specific format for JSON files, so you must use csv format with FIELDTERMINATOR, FIELDQUOTE, and ROWTERMINATOR set to 0x0b, and a schema that includes a single NVARCHAR(MAX) column. The result of this query is a rowset containing a single column of JSON documents.

Use JSON_VALUE function to parse the {json data} into columns, for example:
```sql
SELECT JSON_VALUE(doc, '$.product_name') AS product,
        JSON_VALUE(doc, '$.list_price') AS price
FROM 
    OPENROWSET (
        BULK 'https://mydata.blob.core.windows.net/data/files/*.json',
        FORMAT = 'csv',
        FIELDTERMINATOR = '0x0b',
        FIELDQUOTE = '0x0b',
        ROWTERMINATOR = '0x0b'
        ) WITH (doc NVARCHAR(MAX)) AS ROWS
```

When querying Parquet files:
```sql
SELECT TOP 100 *
FROM OPENROWSET (
    BULK 'https://mydata.blob.core.windows.net/data/files/*.*',
    FORMAT = 'parquet') AS ROWS
```