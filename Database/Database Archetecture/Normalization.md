three rules for organizing data in a database. These are called normalization rules, and they help us to reduce redundancy and improve the integrity of our data. These first three rules, called first, second, and third normal form, are considered to be the standard level of optimization for a business database. Applying these rules is an important step in designing any database. These rules are sets of formal criteria, and they build on top of each other, step by step. We move through the forms as we optimize our database to third normal form. The definitions of these forms are pretty academic, and they're interesting to look up if you're curious about the mathematics behind how databases work. When a normalization rule has been applied to a database, we can say that the database is in that normal form. There are many normal forms beyond third normal form, but we won't cover them here because they get a little bit exotic for a basic database like ours. 

 Normalization helps us prevent problems in working with our data, and the process should be revisited whenever there's a change to the schema or the structure of a database. 

[https://www.guru99.com/database-normalization.html](https://www.guru99.com/database-normalization.html) 

***Normalization*** is the technique of dividing the data into multiple tables to reduce data redundancy and inconsistency and to achieve data integrity.  

	Most database systems are normalized database up to the third normal forms in DBMS. 

On the other hand, ****Denormalization**** is the technique of combining the data into a single table to make data retrieval faster. 

Excel is a denormalized SQL table


## 1NF (First Normal Form) Rules 

-   Each table cell should contain a single value. 
    
-   Each record needs to be unique. 
    

Pros: Ensures that each column in a table contains only atomic values, and each row in the table is unique. 

Cons: May result in duplicate data and require more storage space. 

Trade-offs: Choosing a higher level of normalization may improve data integrity and reduce data inconsistencies but may also impact performance due to additional joins required.

![[GetImage (30).png]]

## 2NF (Second Normal Form) Rules 

-   Rule 1- Be in 1NF 
    
-   Rule 2- Single Column ***Primary Key*** that does not functionally dependent on any subset of candidate key relation 
    

Pros: Helps ensure that all non-key columns are dependent on the table's primary key. 

Cons: May still result in duplicate data and require more storage space. 

Trade-offs: Choosing a higher level of normalization may result in slower performance and more complex queries.

![[GetImage (31).png]]

![[GetImage (32).png]]

![[GetImage (33).png]]

Or create teacher table

## 3NF (Third Normal Form) Rules 

-   Rule 1- Be in 2NF 
    
-   Rule 2- Has no transitive functional dependencies 
    

To move our 2NF table into 3NF, we again need to again divide our table. 

Pros: Helps ensure that non-key columns are dependent only on the table's primary key, and reduces the risk of data inconsistencies. 

Cons: May still result in duplicate data and require more storage space, and may require more complex queries. 

Trade-offs: Choosing a higher level of normalization may result in slower performance and more complex queries.


![[2023-04-18 19.47.01 mailcitytechcuny-my.sharepoint.com 0cb43f67d981.png]]

![[GetImage (34).png]]


![[GetImage (35).png]]

![[GetImage (36).png]]


## BCNF (Boyce-Codd Normal Form) 

Even when a database is in 3rd Normal Form, still there would be anomalies resulted if it has more than one ***Candidate*** Key. 

Sometimes is BCNF is also referred as ***3.5 Normal Form***. 

Pros: Helps ensure that the table is fully normalized and reduces the risk of data inconsistencies. 

Cons: May require more complex queries and result in slower performance. 

Trade-offs: Choosing a higher level of normalization may result in slower performance and more complex queries.

![[GetImage (8).jpeg]]

## 4NF (Fourth Normal Form) Rules 

If ***no*** database table instance contains(***we don’t want anywhere***) two or more, independent and ***multivalued(bad)*** data describing the relevant entity, then it is in 4th Normal Form. 

Pros: Helps ensure that the table is fully normalized and reduces the risk of data inconsistencies and redundancies. 

Cons: May require more complex queries and result in slower performance. 

Trade-offs: Choosing a higher level of normalization may result in slower performance and more complex queries, and may require additional maintenance to ensure that the data remains consistent.


![[GetImage (37).png]]

Don’t want this it is better if separated  

also to be considered multi value you need at <mark style="background: #FFF3A3A6;">least 3 columns</mark> the reason why is because with two columns you can fix the issue  in this example A1 is multivalued but we fixed by making independent rows the <mark style="background: #FFF3A3A6;">2nd rule to be multi value is column A have multiple relationships like how A1 maps to B1 and B2</mark>

![[GetImage (38).png]]

The last requirement to be considered multi valued after meeting 3 coulmn minimum is no <mark style="background: #FFF3A3A6;">relationship between b and c in this example</mark>

![[GetImage (39).png]]

![[GetImage (40).png]]

## 5NF (Fifth Normal Form) Rules 

A table is in 5th Normal Form only if it is in 4NF and <mark style="background: #FFB86CA6;">it cannot be decomposed into any number of smaller tables without loss of data and no join dependencies. </mark>

Pros: 

5NF is the highest level of normalization and provides the most complete normalization of data, which helps to ensure data consistency and eliminates redundancies. 

Reduces data anomalies and inconsistencies, which can help to improve the quality of the data. 

Helps to simplify data maintenance and updates, by reducing the number of tables and dependencies. 

Cons: 

Implementing 5NF can be complex and time-consuming, requiring a deep understanding of the relationships between tables and dependencies. 

It can result in more complex queries, which may impact query performance. 

It may also lead to increased storage requirements, as it may require additional tables to store data. 

Trade-offs:  

The decision to implement 5NF should be based on the specific needs and requirements of the application. While 5NF provides the most complete normalization of data, it may not be necessary or practical for all applications. 

Implementing 5NF can help to improve the quality and consistency of data, but it may also lead to more complex queries and slower query performance. 

Choosing a higher level of normalization can help to improve data integrity but may result in additional storage requirements and more complex database schema. 

In summary, 5NF is a powerful tool for ensuring the consistency and quality of data. However, it can be complex to implement, and may have trade-offs in terms of query performance and storage requirements. Therefore, it is important to carefully consider the specific needs of the application and work with stakeholders to find the right balance between normalization, performance, and maintenance.

![[GetImage (9).jpeg]]

![[GetImage (10).jpeg]]

![[GetImage (11).jpeg]]

<mark style="background: #FFB8EBA6;">Ford could have different supplier or you might be sold a different product the way things are separated on this table </mark>

Since table is broken down and loss of data happened this isn't 5th form but if it could be broken down without loss of data then it would be 5th form also known as join dependency  

## 6NF (Sixth Normal Form) Proposed 

6th Normal Form is not standardized, yet however, it is being discussed by database experts for some time. Hopefully, we would have a clear & standardized definition for 6th Normal Form in the near future… 

That’s all to SQL Normalization!!! 

Ultimately, the choice of normalization level should be driven by the specific needs of the application and the trade-offs between data integrity, query performance, storage efficiency, and maintenance complexity. It's important to carefully consider these factors and work with stakeholders to find the right balance for your specific use case.