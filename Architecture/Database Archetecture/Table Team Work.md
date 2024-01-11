---
tags: 
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---
How Fact Tables and Dimension Tables Work Together


Dimension tables usually list a surrogate primary key (i.e., a data type that consists of a single-column integer) that maps to attributes related to the natural key. Imagine you have a dimension table with information relating to different stores: "Dim_Store" (see Star Schema illustration below). You can assign an ID number to each store and its row of related nonnumerical and other information—like store name, size, location, number of employees, category, etc. As it follows, wherever you list the Store ID number on the fact table ("Fact_Sales"), it will map to that specific row of store data on the "Dim_Store" dimension table. 

Of course, the star schema doesn't stop there—because there are additional points (or dimension tables) with information that links to the fact table. As an example, let's say you want to know the following: 

	How many products were purchased? 

	What products were purchased? 

	In what stores were the products purchased? 

	What were the names and addresses of the products purchased? 

	What brand name manufactured the products purchased? 

	What day of the week did customers make each product purchased? 

To conduct a query like this, you'll need to access data contained in all of the dimension tables (Dim_Date, Dim_Store, and Dim_Product). These are separate databases; however, through the fact table—which serves as a point of integration—you can query all of the data, akin to it being in a single table. And that's how a star schema data warehouse works! 

If you’re currently working on eliminating redundancy and improving accessibility in your data warehouse, it might be a good time to reassess how you connect to and use your BI tools. Fortunately, data management doesn’t have to be overly complex. With Integrate.io, you can seamlessly tie all of your data sources together and create a single source of truth. Start your 14-day free trial today and see for yourself!