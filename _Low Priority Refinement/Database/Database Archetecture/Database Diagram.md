---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
![[DB UML relationship types.jpeg]]



Primary Key:
A Primary Key is a single field selected by the designer to uniquely identify a record in a table (or relation) and cannot be null (empty or unassigned) als. The primary key serves as a unique identifier for each record, ensuring data integrity.

primary can't be changed or repeated in the entity diagram 

Foreign Key:
A Foreign Key is a reference to the Primary Key from one table that is used in another table to establish a connection or relationship between them. It facilitates the linkage between tables and is typically used to maintain referential integrity.

Secondary (or Alternative) Key:
A Secondary Key, also known as an Alternative Key, is any field in a table that is not chosen as the Primary Key or Foreign Key. While it may not uniquely identify records, it provides an alternative means of organizing and accessing data.

One-to-Many Relationship:
In a one-to-many relationship, one record from one table is connected to one or more records in another table. This relationship is depicted by a line with one endpoint representing the "one" side and a symbol like a crow's foot indicating the "many" side. For instance, a Customers table may be linked to a Dishes table, where each customer can have a favorite dish. The Foreign Key, in this case, is placed on the "many" side, representing the connection from many customers to one dish.

Advantages of Using Primary Keys in Relationships:
Using the Primary Key of a related table in another table has several advantages. The primary key remains constant and unique, providing stability and consistency in the relationship. Additionally, it takes up less storage space compared to storing the full-text information, contributing to the efficiency of the database, especially as more entries are added.

Many-to-One Relationship:
While the term "many-to-one" is often used colloquially, in reality, it is still a one-to-many relationship. Whether viewed from the "one" side or the "many" side, the underlying structure of the relationship remains the same. For example, when modeling a connection between a Customers table and a Reservations table, a one-to-many relationship exists, as one customer can have many reservations.

Flexibility in One-to-Many Relationships:
One-to-many relationships provide flexibility by allowing one record to be associated with many records in another table. This flexibility is useful for modeling various connections, such as tracking reservations, where each reservation is linked to a customer using a Foreign Key. This approach simplifies data maintenance and ensures the integrity of the database.

![[Relationship Example.png]]

 Many orders could have many dishes and many dishes could be included in many orders. This is what we draw when we discover that we need this kind of relationship, a line with a crow's foot on each end. And that's a signal to us that we need to do a little more work. In most DBMS tools, we can't model a many-to-many relationship directly, so we need to create a linking table, which has a one-to-many relationship with both of the tables we want to use. We'll name it orders dishes. These linking tables are customarily named by combining the table on the left of the many-to-many relationship with the name of the table on the right. The linking table only needs two columns, an order ID and a dish ID. For each item in an order, we'll add a row for each dish. Then when we want to call up information about a customer's orders, we'll ask the database for rows matching the order numbers, and we'll get back a list of the dishes, or rather, the dish IDs that were part of each order. It could be just one or it could be five, 10, or 50. Doing this keeps our orders table nice and clean while allowing us to record the details of what each order included. And it also let's us easily find out how many orders a particular dish was included in. We could create other many-to-many relationships using linking tables for other associations, like if we wanted to keep track of many dishes that a customer likes, we might make a customers dishes table, or if we had a list of ingredients or allergens, we could create a dishes ingredients table or a dishes allergens table, so we could have that information at our fingertips for printing up detailed menus or adding warnings to entries on the menu for someone who might be allergic to an ingredient. We could also model a customer's events linking table. If a customer attends or is interested in attending various events offered throughout the year. Like the previous linking table, this would involve just a customer ID and an event ID with one row for each event the customer plants to attend. And in building this, we'll also be able to get a list of which events specific customers are interested in to help us with our planning. Many-to-many relationships are fairly common, but they're really made up of one-to-many relationships with the addition of a linking table. As you model your database, keep in mind that you might need to add in some linking tables to fulfill certain relationships. Remember, designing a database with ER diagrams is an iterative process. You don't have to get it just right on the first try. 

one-to-one. This is not frequently used, because usually if there's only one row that associates with only one other row, it suggests that the two rows should just be one row and one table. Our database here doesn't have anything that needs a one-to-one relationship. But a real-world example of a one-to-one relationship involves security. We could separate our customers table into two tables, putting just the customers' name and ID in one table and their personal information in the other. Then we'd have a one-to-one relationship between the tables. We might choose to protect the customers' personal information, like their birthday or email address, from being viewed by our employees, while leaving their name and key available to use in other relationships, like printing place cards or looking up a reservation. We might also use a one-to-one relationship if we were assigning resources of some kind, like aprons or chef's hats or iPads, from a table of equipment. If we assign one item to one person, it's not available to be assigned to another person. And one person couldn't be assigned more than one item. Chances are in a real-life scenario, you'd handle equipment assignment differently than this, but that's another way to think about it. One-to-one relationships are indicated by a line with just one endpoint on either side. Some DBMS tools will allow you to secure individual columns of data. So, depending on your implementation, building a relationship like this may not be necessary to protect information. It certainly makes more sense to keep related information together, but various restrictions might require you to separate information. Doing so is an example of denormalization, as we'll see in a little bit. 

referential integrity, which means the database will be aware of the relationship and will not let you or another user modify data in a way that violates that relationship. This helps us to maintain the consistency of the database.


![[Relationship Example Two.png]]


![[Relationship Example Three.png]]

