---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
The relationships between these entities would be:  
  
A Skill Category would have many Skills.  
  
A Skill would belong to one Skill Category and would have many related Skills.  
  
A Demand record would belong to one Skill.  
  
A Resume would have many Skill Experience records.  
  
A Skill Experience record would belong to one Resume and one Skill.  
  
A Matching record would belong to one Resume and one Skill.  
  
A Job would have many Job Skill records.  
  
A Job Skill record would belong to one Job and one Skill.  
  
A Job Match record would belong to one Job and one Resume.



Relational databases use a schema to define tables and the relationships between them. They are based on the relational model, emphasizing data consistency and integrity.

A simple relational model representation


![[relational model.png]]



relational database representation

and simple query examples

```sql
-- INSERT
INSERT INTO customers (first_name, last_name, email)
VALUES ('John', 'Doe', 'john.doe@example.com');

-- UPDATE
UPDATE customers
SET email = 'john.doe_updated@example.com'
WHERE id = 1;

-- DELETE
DELETE FROM customers
WHERE id = 1;>)](<-- SELECT
SELECT * FROM customers;

-- INSERT
INSERT INTO customers (first_name, last_name, email)
VALUES ('John', 'Doe', 'john.doe@example.com');

-- UPDATE
UPDATE customers
SET email = 'john.doe_updated@example.com'
WHERE id = 1;

-- DELETE
DELETE FROM customers
WHERE id = 1;>)
```

