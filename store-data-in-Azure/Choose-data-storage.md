## Introduction

Data comes in different shapes and sizes. No signle solution fits all data. Each dataset has different requirements. It's your job to figure out which storage solution is best. The key factors to consider in deciding on the optimal storage solution are: 
- how to classify your data, 
- how your data will be used, 
- and how you can get the best performance for your application. 

## Classify your data

Application data can be classified into one of three ways: 
- structured (aka, *relational data*)
    - all data has the same fields or properties
    - all data has the same organization and shape, or schema => shared schema allows data be easily searched by SQL
- semi-structured (aka, non-relational or not only SQL, NoSQL, data)
    - less organized than structured data
    - isn't stored in a relational format because the fields don't fit neatly into tables, rows, and columns
    - contains tags that make the organization and hierarchy of the data apparent => example: key/value pairs
    - the data is defined by a data serialization language => serialization is the process of converting data into a format that can be transmittted or stored
    - software developers use data serialization languages to write data stored in memory to file, which can then be sent to another system, parsed, and read. The sender and receiver don't need to know details about the other system. As long as the same serialization language is used, the data can be understood by both system. Common serialization languages: XML, JSON, YAML.
        - Extensible Markup Language (XML) was one of the first data languages to be widely used. XML expresses the shape of the data by using tags that are defined inside angle braces. The tags come in two forms: *elements* and *attributes*. Elements can have child elements to express relationships. XML is flexible and can express complex data easily. However, it tends to be more verbose, which makes it larger to store, process, and pass over a network. As a result, other formats have become more popular.
        - JavaScript Object Notation (JSON) has a lightweight specification and uses curly braces to indicate data structure. Compared to XML, JSON is less verbose, and it's easier for humans to read. JSON frequently is used by web services to return data. The JSON format isn't as formal as XML. It's closer to a key/value pair model than to a formal data expression. As you might guess from the name, the JavaScript programming language has built-in support for this format, so it's popular for web development. The downside of JSON is that it tends to be more programmer-oriented, so it's harder for non-technical people to read and modify.
        - YAML Ain’t Markup Language (YAML) is a more recently developed data serialization language. One of the benefits of using YAML is that it's easier for humans to read than some other languages. The data structure is defined by line separation and indentation. The YAML format reduces the dependency on structural characters like parentheses, commas, and brackets. This format is more readable than JSON, and it's often used for configuration files that need to be written by people but parsed by programs. YAML is the newest of these data formats.
- unstructured
    - data is undefined and is often delivered in file format, such as photo or video files. Photo or video file itself might have an overall structure and come with semi-structured metadata, but the data that forms the photo or video is unstructured. Other unstrctured data examples: photos, videos, audios, Word documents, text files, log files

## Determine operational needs

Ask these questions about your data:
- Will you be doing simple lookups by using an ID field?
- Do you need to query the database for one or more fields?
- How many create, update, and delete operations do you expect to run?
- Do you need to run complex analytical queries?
- How quickly do these operations need to process?

## Group multiple operations in a transaction

If a change to one piece of data must result in a change to another piece of data, an application needs to group together a series of data updates. You can use transactions to group these updates. In a transaction, if one event in a series of updates fails, the entire series can be rolled back or undone.

An example is an online retailer that uses a transaction to place an order, verify payment, and update the product inventory. Grouping the related events ensures that you don't reduce your inventory levels until you receive an approved form of payment.

### What is transaction?

A logical group of database operations that run together. Here's the question to ask yourself regarding whether you need to use transactions in your application: Will a change to one piece of data in your dataset affect another piece of data? If the answer is yes, you'll need support for transactions in your database service.

Transactions are often defined by a set of four requirements call ACID guarantees. ACID is an acronym for atomicity, consistency, isolation, and durability.

- Atomicity means a transaction must run exactly once, and it must be atomic. Either all of the work is done or none of it is. Operations within a transaction usually share a common intent and are interdependent.
- Consistency ensures that the data is consistent both before and after the transaction.
- Isolation ensures that each transaction is unaffected by other transactions.
- Durability means that changes made as a result of a transaction are permanently saved in the system. The system saves data that's committed so that even in the event of a failure and system restart, the data is available in its correct state.
When a database offers ACID guarantees, these principles are consistently applied to each transaction.

### OLTP vs. OLAP

Transactional databases are often called online transaction processing (OLTP) systems. OLTP systems commonly support many users, have quick response times, and handle large volumes of data. They also are highly available, which means they have minimal downtime. OLTP systems typically handle small transactions or relatively simple transactions. Example: Azure SQL Database

Online analytical processing (OLAP) systems commonly support fewer users, have longer response times, can be less available, and typically handle large transactions or complex transactions. Example: Azure Analysis Services

## Choose a storage solution on Azure

### Case I: Product catalog data

- semi-structured data
- Azure Cosmos DB

### Case II: Photos and videos

- unstructured data
- Azure Blob Storage

### Case III: Business data

- structured data
- Azure SQL Database
