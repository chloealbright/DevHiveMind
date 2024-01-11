---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---


A relational database is one which employs the relational model, in which the raw data is organized into sets of tuples, and the tuples organized into relations. This relational model imposes structure on its contents, in contrast to unstructured or semi-structured data of the various NoSQL architectures. 

tuple (plural tuples) 

1.  (set theory) A finite sequence of terms.  
    
2.  (databases) A single row in a relational database. 
    
3.  (computing) A set of comma-separated values passed to a program or operating system as a parameter to a function call. 
    
4.  (programming) A fixed-size container data type similar to a list that can hold different types of elements. 
    
    Both Python and Haskell have a tuple data type as well as a list data type. 
    
    Unlike lists, tuples are not formed by consing. 


 A record is a full row with values from all columns and a tuple is a partial row with values from specific columns 

These DB has tables with rows & columns which are referred to sometimes as Field & Records 

Multiple tables with no relationships are referred to as entices  

SQL can be used both as a DDL, or data definition language, and a DML, or a data manipulation language. When we create a database or modify its schema, we'll use SQL as a DDL, and when we work with data inside the structure of a database, we'll use SQL as a DML. As an example, I'll step through the creation of one of the tables we designed earlier. Keep in mind, though, you don't need to follow along with this. I just want to show you how it's done in general. As you learn more about databases, about SQL, and about your DBMS in particular, you'll learn how to do this on your system. Before we define tables, we need to create a database, and in SQL, that's done like this. Sometimes we need to tell a system to use our newly created database. Now that I have a database, I'm going to switch over to software that will let me show you SQL statements and their results. For the rest of this chapter, I'll go through some examples using SQL that you can watch but that you don't need to follow along with. If you have a DBMS to use, that's great, but the intention here is just to show you how SQL queries work in general. 

When we create db we use SQL as a DDL and when inside we use SQL as a DML 

Making something not null means it is required  

You can use REFERENCE newName(othertablePrimaryKeyID) to refer othertablePrimaryKeyID as a foreign key but with name of newName 

To find date range you can do this Select .. From … Where Date > specify date AND Date < specify date 

In the relational model, a primary key is a single attribute, or combination of attributes, which can be used to uniquely identify a row of data in a given table. Common primary keys include vendor ID, user ID, email address, or combination of attributes considered together such as first name, last name, and city of residence, all considered together as a single entity. It should be noted that what is an acceptable primary key in one situation may not uniquely identify data instances in another. 

Again in the relational model, a foreign key is an attribute or collection of attributes from one relational table whose values must match another relational table's primary key. A common use for such an organizational scheme would be to link a street address in one table to a city in another, and perhaps to a country in a third. This eliminates repetitive data input, and reduces the possibility of error, increasing data accuracy. 

What Is a Composite Key in SQL?  

A composite key in SQL can be defined as a combination of multiple columns, and these columns are used to identify all the rows that are involved uniquely. Even though a single column can’t identify any row uniquely, a combination of over one column can uniquely identify any record. In other words, the combination key can also be described as a primary key that is being created by using multiple columns. However, the data types of different columns could differ from each other. You can also combine all the foreign keys to create a composite key in SQL. 

A unique key is a constraint in SQL which helps in uniquely identifying a record in the data table. It is can be considered somewhat similar to the Primary key as both of them guarantees the uniqueness of a record. But unlike primary key, a unique key can accept NULL values and it can be used on more than one column of the data table. 

DB transaction follow ACID(Atomic Consistent Isolated Durable)  

 Atomic here means that the transaction is indivisible, that pieces of it can't be separated out. Consistency means that whatever the transaction does, it needs to leave the database in a valid or consistent state. The actions in a transaction can't violate integrity rules that are defined for the database. Isolation means that while the activities in the transaction are being completed, nothing else can make changes to the data involved. If we were in the middle of moving money from one account to another, and the user submitted another transfer request, that request would have to wait until the first one finishes completely. Durability means that the information we change in the transaction actually gets written to the database. When the transaction is reported as complete, the data is there. The change has been made.  

If error occurs during transaction and a step isn't completed the transaction changes are undone  

MySQL, an open-source DBMS that includes a few other useful features on top of the SQL standard. SQL allows us to write statements which the DBMS interprets, and that's how we interact with the data in the database, from apps, or even within the DBMS itself. 

An associative table is a non-prime table whose primary key columns are all foreign keys. 

Because associative tables model pure relationships rather than entities, the rows of an associative table do not represent entities. Instead, they describe the relationships among the entities the table represents. 

Always define all your prime tables before defining any associative tables. 

when records need to be related in a many-to-many relationship  An associative (or linking) table relates foreign keys from different tables to associate their records. 

 TIMESTAMP is great for recording when an order was placed, for example. We'll use DATE for the Birthday field, and DATETIME for events and reservations, because the time as well as the date, is important for those. 

. Null is a value that represents the absence of a value. It's often used to represent a missing value in a database. If we don't have someone's phone number, we don't store the value false, for example, or a placeholder like zero. We use null to indicate that a value is missing rather than some placeholder value that might cause problems later on. Null isn't a data type. It's more of a condition. We talk about no values as being null or not null rather than being equal to null. If there's a value in a cell, than the cell, whatever type it is, is not null. Even if a cell contains the text "null," it's not null. If there's a missing value, no value at all, not even false or zero, that value is null. And when we define the columns later on, we'll have the opportunity to say whether a column can contain null values and whether the default value for a column is null or something else. 

There's another kind of key too called a composite key. This is what we get when we use more than one field to uniquely identify a record. A composite key might be a combination of a first name, last name, and phone number, if the combination of all of those values is unique for every row. Usually, we'll want to use a single key, but if for some reason we can't add a key column to a particular table, and that table doesn't have one single column that can act as a natural key, we may need to use a composite key instead. We've defined all the primary keys that we'll need for now. In a little bit, we'll see how to use these as foreign keys, but first, we need to explore relationships between tables. 

If you don't use a number type to store numeric data 

you need to take additional steps to process the data as a number whenever you use it 

Storing numeric data in numeric data types gives you the ability to work with numbers directly, as you might do when you use mathematical operations in queries. 

- Indexes, transactions, and stored procedures are all features offered by most DBMS tools. How they are used and how you choose to apply them will vary based on the software and your needs. Just like in a book, tables in a database can have indexes, where you can look up information quickly. A primary key acts as an index, but sometimes, especially on large tables, you may want to look up other fields. Normally, this involves scanning the whole table for matching terms. For example, on a table with many customers, we might want to look up customers directly by name. We could search using the first name and last name fields. On a large table, this kind of search might take a while, as the database compares those fields in each row with the search term. But with an index on those fields, the database stores a reference to what each value is in those fields and where it's located, and using that index, the database can return information much faster, but when we add indexes, it increases the amount of time some operations, like inserting a record, will take. So like many optimizations you might make to a database, there is a trade-off. Even though I mentioned transactions earlier, I want to touch on them here again. Once you learn to read SQL, it's easy to write up some queries and statements and just start using your database through a command prompt or in an app. Constraints that you put in place can help protect data, but it's still important to make sure your queries aren't causing integrity problems with the database. And so it's helpful to remember what transactions are, how they work and when you might need them in working with your data. Transactions group queries or statements into a block of activities, where, if one of the components fails for any reason, the whole group of statements is not executed, and anything that's partially done is rolled back. This helps to guarantee that an action isn't only partially applied, leaving the database in an inconsistent state. That means you'll need to think carefully about a whole action that you're planning to do, what steps need to be taken, what business rules need to be applied, and which pieces of data are affected. Creating a transaction in different DBMS tools will be done differently depending on the software, but across the different types of tools, the concept is the same. Many DBMS tools offer a feature called stored procedures. A stored procedure is kind of like a program you write that's stored on the database server. It contains a series of commands that you can then reference and use when you interact with the database. Using a stored procedure, you can avoid having to write out a long or detailed query if it's something you use frequently. Stored procedures are also used to provide safe or approved ways of dealing with sensitive data. Instead of allowing access to data directly from manually entered SQL, which could contain errors, a database administrator often provides a set of stored procedures designed to take certain input, run transactions, and verify a result of a query. In many cases, access to certain sensitive data or whole tables is only allowed through stored procedures rather than directly. As you learn more about your tools and develop your use case, be sure to keep indexes, transactions, and stored procedures in mind to help improve the speed, integrity, and consistency of your database. 









## Foreign Key Referential Actions 

Referential integrity is [constrained by foreign keys](https://www.w3schools.com/sql/sql_foreignkey.asp), ensuring that values in a particular table match values that are found in a different table. 

These referential actions reinforce the integrity of the table structure, reducing the possibility of error by ensuring that referenced columns only contain unique sets of values. 

Foreign keys can also accept null values, but it’s important to note that this may restrict their ability to protect the integrity of the referenced column, as null values are not checked. 

***Tip***: Best practices indicate using a <mark style="background: #FF5582A6;">NOT NULL</mark> constraint when creating foreign keys to maintain the structural integrity of the database. 

Creating a data structure that is flexible and extensible enough for long-term use can become increasingly difficult as data complexity and volume soars. The addition of unstructured data can easily result in errors. 

Foreign keys are an extremely valuable component, helping ensure that your database is clear, consistent, and able to rapidly deliver accurate results. 

  