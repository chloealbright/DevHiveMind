---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Use [Hadoop](https://hadoop.apache.org/) for fast data processing for large amount of data


If you use other databases like an H2 in embedded mode it can help in terms of running a database in a restricted environment like TD but it restricts the access of the database to external services that you may want to connect to




SQL is a declarative language  

Relational databases RDB used a lot for banking, content management systems like WordPress, etc .. 

A relational database is one which employs the relational model, in which the raw data is organized into sets of tuples, and the tuples organized into relations. This relational model imposes structure on its contents, in contrast to unstructured or semi-structured data of the various NoSQL architectures. 

tuple (plural tuples) 

1.  (set theory) A finite sequence of terms.  
    
2.  (databases) A single row in a relational database. 
    
3.  (computing) A set of comma-separated values passed to a program or operating system as a parameter to a function call. 
    
4.  (programming) A fixed-size container data type similar to a list that can hold different types of elements. 
    
    Both Python and Haskell have a tuple data type as well as a list data type. 
    
    Unlike lists, tuples are not formed by consing. 
    

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

WHERE CustomerName LIKE 'a%' Finds any values that start with "a" 

%a or ends with a 

Or %on% will find values with on 

b%n starts with end with n 

You can also specify an OFFSET from where to start returning data. 

LIMIT 10 OFFSET 5 

Returns records 6 through 15 

Good way to see query res of two tables joined then work on specification 

select *  

from people 

join states  

on people.state_code = states.state_abbrev 

We can also ask for data across tables without using the join keyword and just using the dot notation for the table names and the fields on them. Well, that works just the same as writing join explicitly. In fact, this is called an implicit joint, when we don't write it. It's usually best to use the explicit join syntax, just to keep things clear. It's also possible to end up with unintended consequences, like a cross join, when using an implicit join, so be sure to use explicit join syntax to avoid that.  

select people.first_name, states.state_name  

from people, states  

where people.state_code = states.state_abbrev; 

Make sure when you group by it makes sense  

select state_code, quiz_points, COUNT(quiz_points) 

from people  

GROUP BY state_code, quiz_points; 

Groups people who are getting hats by state  

select states.state_name, COUNT(people.shirt_or_hat) 

from states  

join people on states.state_abbrev=people.state_code 

where people.shirt_or_hat='hat' 

group by people.shirt_or_hat, states.state_name  ; 

Sometimes we need to use more than one select statement to get the information we want. It's often the case that we want to set up a query that relies on the result of another query. Using a secondary select statement inside of another query is called a sub-query or sub-select, and it helps us to narrow down or zero in on a specific set of data to use in that larger query.  

select * 

from people  

where state_code=( 

SELECT state_abbrev FROM states WHERE state_name='Kansas' 

); 

Create select statement first before doing an Update or Delete 

Create Table name( 

Id INT Primary Key NOT NULL AUTO_INCREMENT, 

… 

)






In SQL, you should, in most circumstances, specify explicitly whether a column should or shouldn’t allow NULL values. It isn’t a good idea to rely on defaults, and assume that, if don’t specify the nullability of a column explicitly, using NULL or NOT NULL, then the column should be nullable. The rules that govern what happens if you leave out that option for a given datatype are quite difficult to explain, and even if you understand them, will your team or successors be as willing to do so? 

The reason you need to specify this is because a relational database is designed to make it efficient to prevent bad data getting in. Constraints are the means of doing this. You must therefore use NOT NULL for all columns that cannot legitimately contain nulls. If you specify that a column is NOT NULL, you are defining a constraint that ensures that that the column can never hold or accept NULL, so you can’t accidentally leave the value out. By allowing null values in a column you also makes aggregation trickier and can make WHERE clauses give unexpected results unless you use functions such as ISNULL(), IFNULL(), and NULLIF() for handling nulls. 

Don’t assume that the column will allow nulls if you don’t specify it. This article will explain why you should always specify whether a column that you are defining in any table allows null values. It cannot go too far into the issue of whether NOT NULL constraints are a good thing, but just explains why you need to state your preference. 

You might think that if you don’t include the NOT NULL constraint in the column’s definition, then the column will be nullable. No, wrong. It may be nullable, but it may not. It depends on the datatype, the database settings and the settings of the connection. Unless you can memorize all the rules and guarantee the type of connection used for your DDL scripts, it is much simpler just to accept the single rule that you always specify whether your columns are NULL or NOT NULL. 

We’ll now look at the various factors that could determine whether a column gets a NOT NULL constraint, if you don’t specify it.






-   DDL – Data Definition Language  
    
    -   used to define the database schema. 
        
    -   CREATE, DROP, ALTER 
        
-   DQL – Data Query Language  
    
    -   used for performing queries on the data within schema objects. 
        
    -   SELECT 
        
-   DML – Data Manipulation Language  
    
    -   used for manipulation of data present in the database 
        
    -   INSERT, UPDATE, DELETE 
        
-   DCL – Data Control Language  
    
    -   deals with the database system's rights, permissions, and other controls. 
        
    -   GRANT, REVOKE

