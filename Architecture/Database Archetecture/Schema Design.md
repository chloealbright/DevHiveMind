---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
In computer programming, a schema (pronounced SKEE-mah) is the organization or structure for a database , while in AI a schema is a formal expression of an inference rule.




A database schema is like a skeletal structure representing a logical view of a whole database. It devises all the constraints applied to the data in a particular database. Whenever organizations engage in data modeling, it leads to a schema.



Database schema ends up influencing how you build out features in terms of the order of features you build



Data modeling is the process of creating a simplified diagram of a software system and the data elements it contains, using text and symbols to represent the data and how it flows. Data models provide a blueprint for designing a new database or re-engineering a legacy application. Overall, data modeling helps an organization use its data effectively to meet business needs for information.

A data model can be thought of as a flowchart that illustrates data entities, their attributes and the relationships between entities. It enables [data management](https://www.techtarget.com/searchdatamanagement/definition/data-management) and analytics teams to document data requirements for applications and identify errors in development plans before any code is written.

Alternatively, data models can be created through reverse-engineering efforts that extract them from existing systems. That's done to document the structure of [relational databases](https://www.techtarget.com/searchdatamanagement/definition/relational-database) that were built on an ad hoc basis without upfront data modeling and to define schemas for sets of raw data stored in [data lakes](https://www.techtarget.com/searchdatamanagement/definition/data-lake) or [NoSQL](https://www.techtarget.com/searchdatamanagement/definition/NoSQL-Not-Only-SQL) databases to support specific analytics applications.



A database schema is (generally) broadly divided into two categories: physical database schema that defines how the data-like files are actually stored; and logical database schema, which describes all the logical constraints -- including integrity, tables and views -- applied on the stored data.



### What is a schema in SEO?

When it comes to search engine optimization (SEO), schemas play a critical role in defining the different entities on a website. This means that schemas help to clearly explain the relationships among people, products and things to web crawlers. By providing this extra content, sites can help search crawlers successfully match search intent with content.

Schemas define the asset type that web crawlers can quickly crawl through without any added visibility or extra context that often leads to latency. This approach also helps enhance search engine results page ([SERP](https://www.techtarget.com/whatis/definition/search-engine-results-page-SERP)) visibility for images, videos, FAQs and more.

Schema markup or labels coded in [HTML](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics) adds context and shares important information about website pages. It essentially acts as an HTML signpost for spiders that crawl through your content and provide rich snippets in search results.


### What is an API schema?

APIs ([application programming interfaces](https://www.techtarget.com/searchapparchitecture/definition/application-program-interface-API)) enable disparate pieces of software, services and platforms to share information and interact. Inspired by database schema, an API schema aims to bring that same sort of guide/connectors/descriptors to various aspects of application development to programmers and their APIs.

The creation of [API Description Languages](https://www.techtarget.com/searchapparchitecture/tip/Think-carefully-about-API-language-standards) (API DL) first enabled API schema, which later led to today's [OpenAPI standard](https://www.techtarget.com/searchapparchitecture/definition/OpenAPI-Specification). Readable by both humans and machines, API schema describes [RESTful API](https://www.techtarget.com/searchapparchitecture/definition/RESTful-API) operations and methods for interacting with APIs.

Think of an API schema as a virtual instruction manual amplifying programming processes. It makes APIs easier to use and more discoverable and -- when well executed – enables the creation of SDKs and machine-generated API documentation.




# OG 
Database schema design refers to the strategies and practices for constructing a database schema. 

A database schema is a description of how data is structured or organized in a database.  

There are six types of database schemas: flat model, hierarchical model, network model, relational model, star schema, and snowflake schema.  

The term database schema is most commonly used for relational databases, which organize information in tables and use the SQL query language. Non-relational (or “NoSQL”) databases come in several different formats and don't have a “schema” in the same way that relational databases do (although they do have an underlying structure). 

There are two fundamental components of any database schema: 

Physical database schema: The physical database schema describes how you physically store data in a storage system and the form of storage used (files, key-value pairs, indices, etc.). 

Logical database schema: The logical database schema describes the logical constraints applied to data and defines fields, tables, relations, views, integrity constraints, etc. These requirements provide useful information for programmers to apply to the physical design of a database. The rules or constraints defined in this logical model determine how data in different tables relate to one another. 

The definition of physical tables in the schema comes from the logical data model. Entities become tables, entity attributes become table fields, etc. 

Why is Choosing The Right Schema Important? 

Choosing the wrong database schema for a project can lead to debilitating bottlenecks in an application and costly refactoring. For example, if you didn't realize early on that your application would rely on several table JOINs, your service will eventually grind to a halt when you reach a certain number of users and data.  

To resolve this, data will likely have to move to new tables, code will have to point to those new tables, and then those tables will need the proper JOINs. This means you will need a strong test environment (database and source code) to test your changes, a plan to manage data integrity, and a plan for updating your database and source code simultaneously. 

Once you start migrating your database to a new schema, there is almost no turning back. Choosing the correct database schema in the first phase can eliminate a lot of anguish and heartache throughout the life of a software project 

Flat model: A flat model database schema organizes data in a single, two-dimensional display—think of a Microsoft Excel spreadsheet or a CSV file. This schema is best for simple tables and databases without complex relationships between different entities. Also good for simple apps/ 

Hierarchical model: Database schemas in a hierarchical model have a “tree-like” structure, with child nodes branching out from a root data node. This schema is ideal for storing nested data—for example, family trees or biological taxonomies. A good example of this model is JSON or XML 

Network model: The network model, like the hierarchical model, treats data as nodes connected to one other; however, it allows for more complex connections, such as many-to-many relationships and cycles. This schema can model the movement of goods and materials between locations or the workflows required to accomplish a particular task. Like a graph. 

Relational model: As discussed above, this model organizes data in a series of tables, rows, and columns, creating relationships between different entities. The next section and the rest of this guide will focus on the relational model.  

Star schema: The star schema is an evolution of the relational model that organizes data into facts and dimensions. Fact data is numerical (for example, the number of sales of a product), while dimensional data is descriptive (for example, a product’s price, color, weight, etc.). 

Snowflake schema: The snowflake schema is a further abstraction on top of the star schema. It contains a fact table that connects to a dimensional table, expanding the descriptiveness possible within a database. As you might have guessed, the snowflake schema gets its name from the intricate patterns of a snowflake, where smaller structures radiate off of the central arms of the flake.  

A star schema has denormalized dimension tables, while a snowflake schema has normalized dimension tables. A star schema is easier to design and implement than a snowflake schema. A star schema can be more efficient to query than a snowflake schema, because there are fewer JOINs between tables. 

A star schema can require more storage space be more difficult to update, and troubleshoot than a snowflake schema, because of the denormalized data. 

Which schema is right for you? 

The answer depends on your specific needs and requirements. If you’re looking for a simple, efficient cloud data warehouse solution, a star schema might be the best option. But if you need more flexibility to accommodate changing data requirements, a snowflake schema may be a better choice.

![[Star vs Snow.png]]


Yes, it is possible to have multiple fact tables in a schema. A fact table in a data warehouse contains the measures or metrics that are being analyzed, such as sales, revenue, or customer interactions. Each fact table represents a different aspect of the data being analyzed. 

For example, in a retail company, there might be one fact table for sales data and another fact table for inventory data. Both fact tables would contain different measures, but they would be related to each other through common dimensions such as product, store, and time. 

Having multiple fact tables allows for more complex analysis of the data and enables the creation of reports that provide deeper insights into the business. However, it is important to design the schema carefully to ensure that the relationships between the tables are properly defined and that queries can be executed efficiently. 

Yes, it is possible to have more fact tables than dimensional tables in a schema, although it is not the most common scenario. 

The number of fact tables and dimensional tables in a schema depends on the nature and complexity of the data being analyzed. In some cases, there may be multiple fact tables with different measures and different levels of granularity, but fewer dimensional tables that are shared between them. 

For example, in a customer relationship management system, there might be multiple fact tables for different types of interactions with customers, such as phone calls, emails, and chat sessions. Each fact table would contain different measures such as call duration, email response time, or chat transcript length. However, there might be only one dimensional table for customer data, which is shared between the fact tables. 

In general, it is important to design a schema that reflects the relationships and hierarchy of the data being analyzed, and to ensure that queries can be executed efficiently. 




Most common types of dimension tables that are used in data warehousing and business intelligence systems include: 

## custom 
Time Dimension Table: This type of table is used to store date and time-related information, such as year, quarter, month, week, day, hour, minute, and second. It can be used to analyze trends and patterns over time. 

Geography Dimension Table: This type of table is used to store geographical information, such as country, state, city, postal code, longitude, and latitude. It can be used to analyze data based on geography. 

Product Dimension Table: This type of table is used to store information about products, such as product name, category, sub-category, brand, model, size, and color. It can be used to analyze sales and inventory data. 

Customer Dimension Table: This type of table is used to store information about customers, such as name, age, gender, address, email, phone number, and loyalty status. It can be used to analyze customer behavior and preferences. 

Salesperson Dimension Table: This type of table is used to store information about salespersons, such as name, department, territory, commission rate, and hire date. It can be used to analyze sales performance and commission payments. 

Promotion Dimension Table: This type of table is used to store information about promotions, such as promotion name, start date, end date, discount rate, and coupon code. It can be used to analyze the effectiveness of marketing campaigns. 

Supplier Dimension Table: This type of table is used to store information about suppliers, such as supplier name, address, contact information, and products supplied. It can be used to analyze supplier performance and relationships. 

These are just a few examples of dimension tables that can be used in a data warehouse or business intelligence system. The specific types of dimension tables used will depend on the data being analyzed and the needs of the organization.

