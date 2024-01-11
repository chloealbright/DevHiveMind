---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---


 A record is a full row with values from all columns and a tuple is a partial row with values from specific columns 

These DB has tables with rows & columns which are referred to sometimes as Field & Records 

Multiple tables with no relationships are referred to as entices  

SQL can be used both as a DDL, or data definition language, and a DML, or a data manipulation language. When we create a database or modify its schema, we'll use SQL as a DDL, and when we work with data inside the structure of a database, we'll use SQL as a DML. As an example, I'll step through the creation of one of the tables we designed earlier. Keep in mind, though, you don't need to follow along with this. I just want to show you how it's done in general. As you learn more about databases, about SQL, and about your DBMS in particular, you'll learn how to do this on your system. Before we define tables, we need to create a database, and in SQL, that's done like this. Sometimes we need to tell a system to use our newly created database. Now that I have a database, I'm going to switch over to software that will let me show you SQL statements and their results. For the rest of this chapter, I'll go through some examples using SQL that you can watch but that you don't need to follow along with. If you have a DBMS to use, that's great, but the intention here is just to show you how SQL queries work in general. 

When establishing a database, SQL serves as the Data Definition Language (DDL) for defining its structure. Once inside the database, SQL transforms into the Data Manipulation Language (DML), enabling operations on the stored data.





MySQL, an open-source DBMS that includes a few other useful features on top of the SQL standard. SQL allows us to write statements which the DBMS interprets, and that's how we interact with the data in the database, from apps, or even within the DBMS itself. 

An associative table is a non-prime table whose primary key columns are all foreign keys. 

Because associative tables model pure relationships rather than entities, the rows of an associative table do not represent entities. Instead, they describe the relationships among the entities the table represents. 

Always define all your prime tables before defining any associative tables. 

when records need to be related in a many-to-many relationship  An associative (or linking) table relates foreign keys from different tables to associate their records. 

 TIMESTAMP is great for recording when an order was placed, for example. We'll use DATE for the Birthday field, and DATETIME for events and reservations, because the time as well as the date, is important for those. 



There's another kind of key too called a composite key. This is what we get when we use more than one field to uniquely identify a record. A composite key might be a combination of a first name, last name, and phone number, if the combination of all of those values is unique for every row. Usually, we'll want to use a single key, but if for some reason we can't add a key column to a particular table, and that table doesn't have one single column that can act as a natural key, we may need to use a composite key instead. We've defined all the primary keys that we'll need for now. In a little bit, we'll see how to use these as foreign keys, but first, we need to explore relationships between tables. 

If you don't use a number type to store numeric data 

you need to take additional steps to process the data as a number whenever you use it 

Storing numeric data in numeric data types gives you the ability to work with numbers directly, as you might do when you use mathematical operations in queries. 









Indexes, transactions, and stored procedures are fundamental features in most Database Management Systems (DBMS), but their utilization and application vary based on the specific software and your requirements.

Much like chapters in a book, database tables can have indexes, allowing for swift information retrieval. While a primary key serves as a default index, large tables may benefit from additional indexes, especially when looking up information based on fields other than the primary key. Although indexes expedite data retrieval, they come with a trade-off, as operations like inserting records may take longer.

Transactions play a pivotal role in maintaining data integrity. They group queries or statements into a cohesive block of activities. If any component fails within the transaction, the entire set of statements is rolled back, ensuring that actions are either fully executed or not at all. Consideration of business rules, data impact, and comprehensive planning is crucial when implementing transactions.

Stored procedures, akin to programs stored on the database server, consist of commands that can be referenced for frequent interactions with the database. They offer a concise alternative to writing lengthy queries and provide a secure means of handling sensitive data. Database administrators often use stored procedures to control access to sensitive data, offering a controlled interface for executing transactions and ensuring query accuracy.

As you delve deeper into your DBMS tools, keep in mind the strategic use of indexes, transactions, and stored procedures. Their thoughtful application enhances database speed, integrity, and consistency.