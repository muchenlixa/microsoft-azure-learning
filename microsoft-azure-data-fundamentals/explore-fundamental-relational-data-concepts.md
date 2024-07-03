## Introduction

The relational database model was designed to solve the problem of arbitrary data structures. It provides a standard way of representing and querying data that can be used by any application. Key advantage of relational database model is its use of tables. 

## Understand normalization

Normalization is used for schema design process that minimizes data duplication and enforces data integrity. A simple defintion for practical purposes is:
- separate each entity into its own table
- separate each discrete attribute into its own column
- uniquely identify each entity instance (row) using a primary key
- use foreign key columns to link related entities

## Structured Query Language (SQL)

Some common relational database management systems that use SQL: 
- Microsoft SQL Server - Transact-SQL (T-SQL)
- MySQL
- PostgreSQL - PostgreSQL
- MariaDB
- Oracle - Procedural Language/SQL (PL/SQL)

### SQL statement types

- DDL statements: create, modify, remove tables and other objects in database (table, stored procedures, views, etc)
- DCL statements: database admin use DCL statements to manage access to objects in database by granting, denying or revoking permissions to specific users or groups
- DML statements: retrieve, insert, modify, delete data from tables

## Database objects

- View: a virtual table based on the results of a SELECT query. 
- Store procedure: defines SQL statements that can be run on command. It's also used to encapsulate programmatic logic in a database for actions that applications need to perform when working with data.
- Index: a structure that enables queries to locate rows in a table quickly. Many indexes can be created on the same table. For example, if you wanted to find products based on price, create an index on the price column of product table will be helpful. If you want to search product by name, create an index on the product name column will speed up the search. 
    - index takes storage space and it should be maintained when there's data update in tables 
    - it might not be worthy to have index on a table with only a few rows of data