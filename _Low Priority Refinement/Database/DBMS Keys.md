---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
A database key in the DBMS context refers to either a singular attribute or a combination of attributes that serves the crucial role of uniquely identifying a tuple (row/record) within a relation (table). Beyond mere identification, keys play a pivotal role in establishing relationships across various tables and columns within a relational database.

Each distinct element within a key, known as key values, contributes to the uniqueness of a tuple. By utilizing keys, a robust structure is established, allowing for the correlation of data between different components of the database. This fundamental concept underpins the relational integrity and inter-connectivity within a relational database system.

#### Primary Key
A primary key, such as `ID` or `SSN`, uniquely identifies each record in a table. 

- It may accept null values, but it is generally advisable to enforce uniqueness and non-null constraints.
- Ensures data integrity and uniqueness.
- Used as a reference in foreign keys of other tables.

#### Foreign Key
A foreign key establishes relationships between tables by referencing primary keys in another tabled.

It Enforces referential integrity by ensuring that values in the foreign key match values in the referenced primary key.

#### Foreign Composite Key:
- A foreign key that is composed of multiple columns, referencing a composite primary key in another table.


#### Composite Key
A composite key is a set of two or more attributes ensuring unique tuple identification. Example:

- A key composed of multiple columns to uniquely identify a record.
- Combines two or more attributes to create a unique identifier.

- { Name, Phone }

#### Compound Key:

- Similar to a composite key, a compound key is composed of multiple columns, but these columns may individually represent partial keys.



#### Unique Key
A unique key ensures uniqueness but allows one null value. Examples include `SSN`, `Email`, or { Name, Phone }.


- Similar to a primary key but allows null values.
- Ensures that each value in the field is unique.
- Often used when a column needs to have unique values but doesn't need to serve as the primary key.

#### Super Key
A super key is a set of attributes that uniquely identifies a tuple.

- A set of one or more keys that, taken collectively, can uniquely identify a record in a table.
- Includes more attributes than necessary for uniqueness.

For instance, in an `Employee` table:

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
A candidate key is the minimal super key without overlaps and null values.

- A minimal set of attributes that can uniquely identify a record.
- Among the super keys, a candidate key is chosen as the primary key.

Examples include:
- { ID }
- { SSN }
- { Email }
- { Name, Phone }


#### Alternate Key
Alternate keys are not the primary key, including candidate keys. 

- A candidate key that is not selected as the primary key.
- Often retained as a backup option for uniqueness.

Only one choice for an alternate key is allowed, such as:
- { SSN }



#### Artificial Key
Artificial keys have no business relevance but handle data management challenges. They are often used in complex primary key situations.

#### Surrogate Key
A surrogate key is an auto-generated key used to bring datasets together efficiently, serving as an alternative to a Union, cast, or convert operation.

- A key introduced as an artificial identifier (usually numeric) to serve as the primary key.
- Often used when natural keys are unsuitable or to simplify relationships.

#### Natural Key
A natural key is an alternative key already present in the table and is unique, such as a social security number.

Ensure data integrity by choosing appropriate primary and alternate keys based on the unique characteristics of the data being modeled.


- A key that is derived from the actual data and characteristics of the entity it represents.
- Examples include a person's social security number or a product's serial number.