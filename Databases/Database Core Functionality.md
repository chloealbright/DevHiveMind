---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
A database is a named collection of tables with fields or columns and records or rows. A database can also contain views, indexes, sequences, data types, operators, and functions. 

Besides that they are also constraints which are the rules enforced on the data columns of a table. These are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the database. 

Constraints could be either on a column level or a table level. The column level constraints are applied only to one column, whereas the table level constraints are applied to the whole table. 

Constraints can be specified when a table is created with the CREATE TABLE statement or you can use the ALTER TABLE statement to create constraints even after the table is created.

The following syntax allows us to name FOREIGN KEY constraint: 
```SQL
CREATE TABLE Orders (     
OrderID int NOT NULL,     
OrderNumber int NOT NULL,     
PersonID int,     
PRIMARY KEY (OrderID),     
CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)     
REFERENCES Persons(PersonID) );
```

![[Database Processes.gif]]

![[Sql Exe Order.gif]]


![[Execution Order.jpg]]