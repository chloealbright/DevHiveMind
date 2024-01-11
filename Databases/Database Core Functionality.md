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

Bridging data accurately is a prime directive. Software integrations and the ability to securely share data between applications are all dependent on data integrity and database relationships. 

This is where constraint comes in. Foreign keys are often constrained to ensure the user cannot take actions that would damage dependency links between tables. This also constrains users from entering invalid data. 

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

We can use foreign key restraints to help maintain referential integrity of our foreign key relationships. There are many referential actions we can use for constraint, including: 

- Cascade: when deleting primary key values, the matching column in the child table are deleted 

- Set null: when a referenced row is deleted/altered, the referencing values in the foreign key are set to null 

- Restrict: Values in the parent table cannot be deleted if they are referred by a foreign key. 

- Set default: The foreign key values in the child table are set to a default value if the parent table is altered/deleted 


![[Database Processes.gif]]

![[Sql Exe Order.gif]]


![[Execution Order.jpg]]


## Data Definition

Data refers to facts and statistics collected for reference or analysis, including factual information used as a basis for reasoning, digital information for transmission or processing, and output from sensing devices. Essentially, everything mentioned about data aligns with the broader concept of information.

### Information Definition

Information is knowledge obtained from investigation, study, or instruction. It involves attributes communicated through sequences or arrangements, signals in communication systems, and quantitative measures. Comparatively, information is more valuable than data as it is created through communication after data analysis, highlighting its role in providing insight and knowledge.

### Cardinality in Databases

Cardinality pertains to the number of unique values in a relational table column relative to total rows. Database administrators assess and store cardinality in system tables for optimization purposes. A database not only stores data but ensures growth, change, sharing, speed, searchability, reliability, interdependence, consistency, protection, and security over time.

### Database Complexity

Databases are not merely for storage; they involve structured data with intricate planning. Companies manage multiple databases covering various data scopes. Indexing, serving as an internal map in databases between primary keys and other tables, establishes crucial relationships.