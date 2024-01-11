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
In the context of SQL and relational databases, DCL, DDL, DML, and DQL are the primary sub-languages that cover most of the operations related to database management. However, it's worth noting that there are some additional concepts or features that might be considered separate from these sub-languages:

1. **TCL (Transaction Control Language):**
   - **Purpose:** TCL is used to manage transactions within a database. It includes commands to control the beginning and ending of transactions, as well as to undo or commit changes.
   - **Commands:**
     - `COMMIT`: Saves all changes made during the current transaction.
     - `ROLLBACK`: Undoes changes made during the current transaction.
     - `SAVEPOINT`: Sets a point within a transaction to which you can later roll back.

   Example:
   ```sql
   BEGIN TRANSACTION;
   -- SQL statements
   COMMIT;
   ```

2. **Session Control Statements:**
   - **Purpose:** These statements are used to control the characteristics of a database session.
   - **Commands:**
     - `SET`: Modifies the session-specific settings, such as the isolation level.
     - `USE`: Specifies the default database for a session.

   Example:
   ```sql
   SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
   USE database_name;
   ```

While DCL, DDL, DML, and DQL are fundamental to SQL, TCL and session control statements are additional components that play roles in managing transactions and customizing the behavior of database sessions. The specific features and sub-languages may vary slightly among different database management systems, as some systems may have their own extensions or variations.
![[Sql Exe Order.gif]]


![[Execution Order.jpg]]

