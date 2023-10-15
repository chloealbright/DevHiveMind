dimension tables are normalized.   

use less space to store dimension tables but are more complex.  

have no redundant data, so they're easier to maintain.  

good for data warehouses.  

snowflake schemas provide users with more efficiency when it comes to processing data.  



The purpose of a snowflake schema is to normalize the denormalized data in a star schema. This solves the write command slow-downs and other problems typically associated with “star schemas.” 

The snowflake schema is a “multi-dimensional” structure. At its core are fact tables that connect the information found in the dimension tables, which radiate outward like in the star schema. The difference is that the dimension tables in the snowflake schema divide themselves into more than one table. That creates the snowflake pattern. 

Through this “snowflaking” method, the snowflake schema normalizes the dimension tables it connects with by (1) getting rid of “low cardinality” attributes (that appear multiple times in the parent table); and (2) turning the dimension tables into more than one table, until the dimension tables are completely normalized. 

Like snowflake patterns in nature, the snowflake database becomes exceedingly complex. The schema can produce elaborate data relationships, where child tables have more than one parent table. 

IBM offers an excellent comparison of snowflake schemas versus star schemas, stating: “Star and snowflake schema designs are mechanisms to separate facts and dimensions into separate tables ... A snowflake schema can have any number of dimensions and each dimension can have any number of levels.” 

# Benefits of Snowflake Schemas 

Snowflake schemas offer the following benefits compared to normal star schemas: 

Compatible with many OLAP database modeling tools: Certain OLAP database tools, which data scientists use for data analysis and modeling, are specifically designed to work snowflake data schemas. 

Saves on data storage requirements: Normalizing the data that would typically get denormalized in a star schema can offer a tremendous reduction in disk space requirements. Essentially, this is because you're converting long strings of non-numerical data (the information pertaining to descriptors and names) into numerical keys that are dramatically less taxing from a storage perspective. 

# Challenges of Snowflake Schemas 

There are three potential challenges relating to snowflake schemas: 

Complex data schemas: As you might imagine, snowflake schemas create many levels of complexity while normalizing the attributes of a star schema. This complexity results in more complicated source query joins. In offering a more efficient way to store data, snowflake can result in performance declines while browsing these complex joins. Still, processing technology advancements have resulted in improved snowflake schema query performance in recent years, which is one of the reasons why snowflake schemas are rising in popularity. 

Slower at processing cube data: In a snowflake schema, the complex joins result in slower cube data processing. The star schema is generally better for cube data processing. 

Lower data integrity levels: While snowflake schemas offer greater normalization and fewer risks of data corruption after performing UPDATE and INSERT commands, they do not provide the level of transnational assurance that comes with a traditional, highly-normalized database structure. Therefore, when loading data into a snowflake schema, it's vital to be careful and double-check the quality of information post-loading.