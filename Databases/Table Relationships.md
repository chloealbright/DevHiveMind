---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Database relationships are associations between tables that are created using join statements to retrieve data. 

In the Database Configuration application, you can define Structured Query Language (SQL) statements for joins, and create relationships between parent and child objects. You can use a join to link data from multiple objects. The parent is the existing object and the child is the object that you are create. 




Data tables and relationships can change in codebase a lot endpoints are structured in order of db table dependencies. you can append data to data not in tables using interfaces when process network request body 

Most common relationships is between many to one or vise vera one to many 

Then one to one 


One side means unique value many means duplicate value 


One to one means both sides have unique values  

Many to many means both can have duplicates  


Stick to only one to one and many to one and one to many relationship  



One to many example 

You have a table of customers for alcohol then you have a table for order IDs that has a phone key of customer ID that is the primary key of the customer table and you have duplicate customer IDs entered for the same person because that person can have many orders for different products or the same products on different dates 

You can have multiple relationships between tables but only one active at a time but that is where conditional things can occur that switches between active and non-active for each relationship  

Just think about it as 1 table column whatever it's called can have multiple records 

Or in this case multiple orders 

A junction table is a table with multiple phone keys like let's say you have a rental table and a movie table you'll have a movie rental table with the primary key coming from movie and rental which would be the foreign key inside of the movie rental table 

Hey junction table is also considered a many to many relationship 

Many to many relationships are used because records in both entities may reference multiple records in each other's entities though and intermediate entity is required known as a junction to compile the multiple records 

Entity a thing with distinct and independent existence. 

The use of the junction table takes your data to its lowest possible normalised level, it should be used where there is something that could be duplicated across multiple entires such as a date or a time. 

Or an example is patience and doctors you can have a junction table that has the primary keys of doctor ID and patient ID 

Then you can create another table relationship between doctors and appointments and patience and procedures 





And power BI when you have multiple relationships you want to link go to edit query  

Go to the table select to or whatever amount of columns you want to have multiple relationships with 

Go to add column and click merge column which would merge those two columns but keep them along with the emerge output 

Then you can go to another column on the other table and do a merge query that merges those two columns and gives you an output but the other two columns don't exist anymore 

This is under the transform tab 

Power BI should automatically detect the relationship 

But you may need to manually do it if it doesn't




To build a different relationships like one to many tables need to share other content 

Like if you have a geography table and a customer table 

One thing that you can have besides the primary key being a foreign key on the other table 

Is something like they both have zip code 

And the ZIP code might not be a primary key just another column on that table but they share it and you can establish that relationship between the tables


### Be aware of Database table relationshapes when coding buisness logic tracflo


**// only subs have crew in the context of a company  

but crew can be  but admin in other companies  

include anything not null-able in fixture  

certain companies dont have equipement or materals  

jjc has equip 

create runtime link from data struc to each data struc section 

need level of detail from project team to formulate business logic 

if you res send and dont add return after it will continue and run other lines of code in your function**
