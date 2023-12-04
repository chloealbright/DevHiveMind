

![[Aggregation and Composition.png]]


![[Association Relationship.png]]

As a data engineer, the first step in determining what type of fact table to use is to understand the business requirements and the data sources that will be used to populate the fact table. Here are some general guidelines for determining the type of fact table to use: 

Identify the grain: The grain of a fact table refers to the level of detail that will be captured in the table. For example, if the fact table is for sales, the grain could be at the transaction level or at a higher level such as daily or monthly sales. Once the grain is identified, it can help determine the type of fact table that will be used. 

Determine the type of measurement: The type of measurement that will be captured in the fact table is another important consideration. There are generally two types of measurements: <mark style="background: #FFF3A3A6;">additive</mark> and <mark style="background: #FFF3A3A6;">semi-additive</mark>. Additive measures can be summed up across dimensions, while semi-additive measures can be summed up for some dimensions but not for others. For example, a sales fact table may have additive measures such as sales revenue, but a semi-additive measure such as inventory levels may be summed up only for time dimensions and not for product dimensions. 

Consider the number of dimensions: The number of dimensions in the fact table is another important consideration. If there are only a few dimensions, a simple fact table may suffice. However, if there are many dimensions, a more complex fact table such as a snowflake schema may be needed. 

Consider the frequency of updates: The frequency of updates to the fact table is also an important consideration. If the fact table is updated frequently, a simpler design may be better. However, if the fact table is updated infrequently, a more complex design may be better. 

Consider the level of aggregation: The level of aggregation is also an important consideration. If the data needs to be aggregated at a very high level, a summary fact table may be appropriate. However, if the data needs to be analyzed at a more detailed level, a transactional fact table may be better. 

In summary, the type of fact table to use depends on the specific business requirements and data sources, the grain of the fact table, the type of measurement, the number of dimensions, the frequency of updates, and the level of aggregation needed. By carefully considering these factors, a data engineer can determine the best type of fact table to use for a given scenario. 

Transact is probably the most used fact table out of them all it is easy simple, most detailed grain, and easiest to do aggerates   also is mostly additive. Largest in size. No updates 

Periodic snapshot would probably be used when you are tracking something like maybe hospital bed status not really doing aggregations. Smaller then transact. No updates 

Accumulating snapshot fact would maybe be used for something like the scale of a amazon and it shipping and phases and tracking things at scale to see what has happened through a period of time. aggregations  are difficult. Smallest in size. Updates after each milestone of specific activities  

The accumulating snapshot fact table is thus a method to measure velocity within the business process. 



GRAIN 

For Transact one row per transaction  

Periodic  one row per time period 

Accumulating one row per entire life time of event 

Fact tables are numerical 

But you can have dimension tables with numbers and it won't be considered a fact table information 

Facts contains quantitative information about business processes for sometimes referred to as measurements or metrics an example  of this is 

Quantity sales amount total earning profit margin total turnover and so on 

When it comes to dimension it can describe people products places time and so on 

Don't create duplicates of dimensions 

Don't consolidate fact tables 

Don't have tables with blank columns when you have large tables


# Role playing dimension  

Role playing dimension means creating a copy of a table in order connect to a table we're you want multiple active relationships  

So you don't have one with multiple relationships we're you have one active relationship and multiple inactive relationship 

In a data warehouse, a role-playing dimension table is a type of dimension table that is used to represent different views of the same underlying data, depending on the context in which it is being used. 

For example, let's say we have a date dimension table in our data warehouse that includes attributes such as year, quarter, month, and day. Depending on the analysis we're doing, we might want to group data by year, or by quarter, or by month. Instead of creating separate tables for each of these views, we can use a single date dimension table and create multiple aliases, or "roles," for it. Each role represents a different perspective on the same data. 

So, for instance, we could create a "Quarter" role for our date dimension table that includes only the quarter attribute and its corresponding key. We could also create a "Month" role that includes only the month attribute and its corresponding key. Each role is essentially a subset of the full date dimension table, with a smaller set of attributes and a smaller set of keys. 

By using role-playing dimension tables, we can simplify our data model and avoid the need to create redundant tables. We can also make it easier to write queries and reports, since we can use the same dimension table in multiple contexts without having to join to different tables or create complex logic. 

It's worth noting that not all dimension tables are suitable for role-playing. Typically, a dimension table that has a hierarchical structure or contains attributes that are not meaningful in all contexts (such as location-specific attributes) is a good candidate for role-playing. On the other hand, a dimension table that represents a standalone entity (such as a product or customer) may not be appropriate for role-playing.