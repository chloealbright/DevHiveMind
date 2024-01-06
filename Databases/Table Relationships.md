---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---


## Most Common Relationships

Consider a one-to-many relationship example: Imagine you have a table for customers purchasing alcohol, and another table for order IDs. The order table contains a foreign key, the customer ID, referencing the primary key of the customer table. Since a customer can place multiple orders for different or similar products on different dates, you might have duplicate customer IDs for the same person in the order table.

While you can have multiple relationships between tables, typically only one is active at a given time. Conditional logic can be employed to switch between active and non-active relationships based on specific criteria.

Think of it as a scenario where a single table column, representing something like customer orders, can accommodate multiple records or orders for the same individual. This setup captures the idea that one customer can have multiple orders, reflecting the one-to-many relationship in the context of the alcohol customer and order tables.






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





In the codebase, data tables and their relationships often undergo changes. Endpoints are organized based on the dependencies of database tables, facilitating a structured approach. When processing network request bodies, data can be appended to fields not present in tables using interfaces.

### Be aware of Database table relationshapes when coding buisness logic tracflo


**// only subs have crew in the context of a company  

but crew can be  but admin in other companies  

include anything not null-able in fixture  

certain companies dont have equipement or materals  

jjc has equip 

create runtime link from data struc to each data struc section 

need level of detail from project team to formulate business logic 

if you res send and dont add return after it will continue and run other lines of code in your function**
