---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
A key in DBMS is an attribute or a set of attributes that help to uniquely identify a tuple (or row) in a relation (or table). Keys are also used to establish relationships between the different tables and columns of a relational database. Individual values in a key are called key values.

#### Primary Key
A primary key, such as `ID` or `SSN`, uniquely identifies each record in a table. It may accept null values, but it is generally advisable to enforce uniqueness and non-null constraints.

#### Super Key
A super key is a set of attributes that uniquely identifies a tuple. For instance, in an `Employee` table:

- { ID }
- { SSN }
- { ID, SSN }
- { ID, Name }
- { ID, Phone }
- { Name, Phone }
- { Name, Email }
- { Name, SSN, Phone }
- { ID, SSN, Phone }

#### Candidate Key
A candidate key is the minimal super key without overlaps and null values. Examples include:
- { ID }
- { SSN }
- { Email }
- { Name, Phone }

#### Composite Key
A composite key is a set of two or more attributes ensuring unique tuple identification. Example:
- { Name, Phone }

#### Alternate Key
Alternate keys are not the primary key, including candidate keys. Only one choice for an alternate key is allowed, such as:
- { SSN }

#### Unique Key
A unique key ensures uniqueness but allows one null value. Examples include `SSN`, `Email`, or { Name, Phone }.

#### Artificial Key
Artificial keys have no business relevance but handle data management challenges. They are often used in complex primary key situations.

#### Foreign Key
A foreign key in a table refers to the primary key in another table.

#### Surrogate Key
A surrogate key is an auto-generated key used to bring datasets together efficiently, serving as an alternative to a Union, cast, or convert operation.

#### Natural Key
A natural key is an alternative key already present in the table and is unique, such as a social security number.

Ensure data integrity by choosing appropriate primary and alternate keys based on the unique characteristics of the data being modeled.