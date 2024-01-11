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

- Indexes, transactions, and stored procedures are all features offered by most DBMS tools. How they are used and how you choose to apply them will vary based on the software and your needs. Just like in a book, tables in a database can have indexes, where you can look up information quickly. A primary key acts as an index, but sometimes, especially on large tables, you may want to look up other fields. Normally, this involves scanning the whole table for matching terms. For example, on a table with many customers, we might want to look up customers directly by name. We could search using the first name and last name fields. On a large table, this kind of search might take a while, as the database compares those fields in each row with the search term. But with an index on those fields, the database stores a reference to what each value is in those fields and where it's located, and using that index, the database can return information much faster, but when we add indexes, it increases the amount of time some operations, like inserting a record, will take. So like many optimizations you might make to a database, there is a trade-off. Even though I mentioned transactions earlier, I want to touch on them here again. Once you learn to read SQL, it's easy to write up some queries and statements and just start using your database through a command prompt or in an app. Constraints that you put in place can help protect data, but it's still important to make sure your queries aren't causing integrity problems with the database. And so it's helpful to remember what transactions are, how they work and when you might need them in working with your data. Transactions group queries or statements into a block of activities, where, if one of the components fails for any reason, the whole group of statements is not executed, and anything that's partially done is rolled back. This helps to guarantee that an action isn't only partially applied, leaving the database in an inconsistent state. That means you'll need to think carefully about a whole action that you're planning to do, what steps need to be taken, what business rules need to be applied, and which pieces of data are affected. Creating a transaction in different DBMS tools will be done differently depending on the software, but across the different types of tools, the concept is the same. Many DBMS tools offer a feature called stored procedures. A stored procedure is kind of like a program you write that's stored on the database server. It contains a series of commands that you can then reference and use when you interact with the database. Using a stored procedure, you can avoid having to write out a long or detailed query if it's something you use frequently. Stored procedures are also used to provide safe or approved ways of dealing with sensitive data. Instead of allowing access to data directly from manually entered SQL, which could contain errors, a database administrator often provides a set of stored procedures designed to take certain input, run transactions, and verify a result of a query. In many cases, access to certain sensitive data or whole tables is only allowed through stored procedures rather than directly. As you learn more about your tools and develop your use case, be sure to keep indexes, transactions, and stored procedures in mind to help improve the speed, integrity, and consistency of your database. 








