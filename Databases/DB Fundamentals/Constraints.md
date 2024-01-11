---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---

    




# Constraint FK

Bridging data accurately is a prime directive. Software integrations and the ability to securely share data between applications are all dependent on data integrity and database relationships. 

This is where constraint comes in. Foreign keys are often constrained to ensure the user cannot take actions that would damage dependency links between tables. This also constrains users from entering invalid data. 

We can use foreign key restraints to help maintain referential integrity of our foreign key relationships. There are many referential actions we can use for constraint, including: 

-   Cascade: when deleting primary key values, the matching column in the child table are deleted 
    
-   Set null: when a referenced row is deleted/altered, the referencing values in the foreign key are set to null 
    
-   Restrict: Values in the parent table cannot be deleted if they are referred by a foreign key. 
    
-   Set default: The foreign key values in the child table are set to a default value if the parent table is altered/deleted 
    

When it comes to foreign key constraint naming, we need to follow these general rules: 

-   The <mark style="background: #FFF3A3A6;">CONSTRAINT</mark> symbol value is used, and it must be unique in the database. 
    
-   For InnoDB tables, a constraint name is generated automatically if the constraint symbol clause is not defined 
    
-   For NDB tables, the <mark style="background: #FFF3A3A6;">FOREIGN KEY index_name</mark> value is used, or a constraint name is generated automatically. 
    

## Foreign Key versus Composite Key 

Composite keys within a relational database are used to combine two or more columns within a ***specific table***, creating a unique identifier for that combination of columns. 

While technically a candidate key as the composite key verifies uniqueness, composite keys are only formed when the particular column or columns are used in combination with each other. 

Like foreign keys, composite keys can be used to link together multiple tables within a relational database. Unlike foreign keys, composite keys can be defined as a primary key during the creation of some SQL tables. 

## Foreign Key Referential Actions 

Referential integrity is [constrained by foreign keys](https://www.w3schools.com/sql/sql_foreignkey.asp), ensuring that values in a particular table match values that are found in a different table. 

These referential actions reinforce the integrity of the table structure, reducing the possibility of error by ensuring that referenced columns only contain unique sets of values. 

Foreign keys can also accept null values, but it’s important to note that this may restrict their ability to protect the integrity of the referenced column, as null values are not checked. 

***Tip***: Best practices indicate using a <mark style="background: #FF5582A6;">NOT NULL</mark> constraint when creating foreign keys to maintain the structural integrity of the database. 

Creating a data structure that is flexible and extensible enough for long-term use can become increasingly difficult as data complexity and volume soars. The addition of unstructured data can easily result in errors. 

Foreign keys are an extremely valuable component, helping ensure that your database is clear, consistent, and able to rapidly deliver accurate results. 

  

MySQL 

```SQL
CREATE TABLE Orders (     
OrderID int NOT NULL,     
OrderNumber int NOT NULL,     
PersonID int,     
PRIMARY KEY (OrderID),     
FOREIGN KEY (PersonID) REFERENCES Persons(PersonID) );  
```

SQL Server 

```SQL
CREATE TABLE Orders (     
OrderID int NOT NULL PRIMARY KEY,     
OrderNumber int NOT NULL,     
PersonID int FOREIGN KEY REFERENCES Persons(PersonID) );  
```

