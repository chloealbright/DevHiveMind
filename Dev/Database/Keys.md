Primary key is ID can also be SSN but might except null valve so maybe not 

Super Key is like a super set It is unique lets say you have a Employee table  

you can Combine the table ID and name Into its Own Column and that Can be a super key or combining name column with another Column outside Of the ID Could be a super Key 

super key can contain null valves name Can't be a super Key in general because you Can have People with the same name 

super key is Collection  

{ ID}  {SSN} 

{ ID, SSN} 

{ ID, Name }  

{ ID , Phone }  

{ Name, Phone }  

{ Name, Email}  

{ Name, SSN, Phone }  

{ ID, SSN, Phone} 

Candidate key  

the minimal of Super key no overlap and can't be null but also unique like PK 

{ ID }  

{ SSN }  

{ Email }  

{ Name, Phone }  

Composite key  

A composite Key is a set of two or more attributes that help identify each tuple in a table uniquely. The attributes in the set may not be unique when considered separately. However, when taken all together, they will ensure uniqueness. The ‘concatenated key’ is another name for a composite key. 

{ Name , Phone } 

Alternate key the key that aren't the primary key So this Includes the Candidate key and anything outside of the Primary key also you can only have one choice for alternate key  

{ SSN }  

Unique key Looks for unique values but can support null valves so SSN would be unique key also Email or { Name , Phone }  

Unique Key is a column or set of columns that uniquely identify each record in a table. All values will have to be unique in this Key. A unique Key differs from a primary key because it can have only one null value, whereas a primary Key cannot have any null values. 

Among the seven types of keys available in the DBMS, a few other types of keys in SQL are also accessible. The key type is called Artificial Keys. An artificial has no relevance or meaning to the business but is often used to tackle conflicting data management situations. For example, if there is no attribute that comprises all required primary key properties or if the primary keys are complex. 

Foreign key a table containing the primary key Of another table 

Surgate key is alternative way to bring to data sets together instead Of using a Union then a cast and Convert 

This key is auto generated when you add a records 

Natrual key Would be an alternative key that is already in the table and is unique like a social security