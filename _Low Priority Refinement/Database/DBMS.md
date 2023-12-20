---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Database Management Systems (DBMS) are software systems used to store, retrieve, and run queries on data. A DBMS serves as an interface between an end-user and a database, allowing users to create, read, update, and delete data in the database.  

A database management system is a software system which facilitates the organization of housed data into a particular database architecture, be it relational (Relational Database Management System, or RDBMS), document store, key-value store, column-oriented, graph, or other. Popular DBMSs include MongoDB, Cassandra, Redis, MySQL, Microsoft SQL Server,  PostgreSQL, SQLite, and Oracle, among many, many, many others.




edit 

column-oriented databases' rows actually contain what we most usually think of as vertical data, or what is traditionally held in relational columns (Rows contains columns? Huh?). The advantage of column-oriented database design is that some types of data lookups can become very fast, given that the desired data could be stored consecutively in a single row (compare this with having to search and read from multiple, nonconsecutive rows to attain the same field value in row-oriented database). Cassandra is a popular example of a column-oriented database. 

 graph database is premised on edges acting as relationships, directly relating data instances to one another. Graph databases have advantages in some use cases, including potentially in certain data mining and pattern recognition scenarios, given that associations between data instances are explicitly stated. Neo4j is the most widely-used graph database available.



Sometimes a database can be a front end while a script in the back end generates the data that populate the databases records or generate a excel spreadsheet




