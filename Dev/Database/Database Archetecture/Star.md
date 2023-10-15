dimension tables are not normalized. 

will only join the fact table with the dimension tables, leading to simpler, faster SQL queries. 

better for datamarts with simple relationships. 

Essentially, star schemas offer users a more efficient way to organize data and information in a data warehouse. 

The center of a star schema consists of one or multiple “fact tables” that index a series of “dimension tables.” 

The fact data gets organized into fact tables and the dimensional data into dimension tables. Fact tables are the points of integration at the center of the star schema in the data warehouse. They allow machine learning tools or OLAP(Online Analytical Processing) systems to analyze the data as a single unit, and they allow other business systems to access the data together. Dimension tables hold and manage the data—numerical and nonnumerical—which converges through fact tables that make up the data warehouse. You also typically have foreign keys in fact tables. 

# Types of Fact Tables 

Transaction fact tables: These record information related to events, like individual merchandise sales. 

Snapshot fact tables: These record information that applies to specific moments in time, like year-end account statements. 

Accumulating snapshot tables: These record information related to a running tally of data, like year-to-date sales figures for specific merchandise or categories of merchandise. 

# Types of Dimension Tables 

#### Dimension tables normally store fewer records than fact tables; however—in addition to storing numerical data—the records in dimension tables also include descriptive attributes. There are many types of dimension tables depending on the information system. Here are some examples: 

Time dimension tables: Information to identify the exact time, date, month, and year different events happened. 

Geography dimension tables: Address/location information. 

Employee dimension tables: Information about employees and salespeople, such as addresses, phone numbers, names, employee numbers, and email addresses. 

Merchandise dimension tables: Descriptive information about products, their product numbers, etc. 

Customer dimension tables: Customer name, numbers, contact information, addresses, etc. 

Range dimension tables: Information relating to a range of values for time, price, and other quantities. 

## Denormalization of Data in Star Schemas 

The star schema’s goal is to speed up read queries and analysis for massive amounts of data contained in diverse databases with different source schemas. The star schema achieves this goal through the “denormalization” of the data within the network of dimension tables. 

Traditionally, database managers sought the “normalization” of data by eliminating duplicate copies of the same data, which is to say, the normalization of the duplicate information into one copy. This made write commands faster because only one copy of the data needed updating. 

When a data system expands into multiple dimension tables, however, accessing and analyzing data from multiple sources slows down read queries and analysis. To speed things up, the star schema relaxes the traditional rules of database normalization by “denormalizing” the data. 

A star schema pulls the fact data (or ID number primary keys) from the dimension tables, duplicates this information, and stores it in the fact table. In that way, the fact table connects all of the information sources together. This makes read queries and analysis infinitely faster. However, it sacrifices the speed of write commands. The slower write commands happen because the system needs to update all counterpart copies of the “denormalized” data following each update. 

## Challenges of Star Schemas 

As mentioned before, improving read queries and analysis in a star schema could involve certain challenges: 

Decreased data integrity: Because of the denormalized data structure, star schemas do not enforce data integrity very well. Although star schemas use countermeasures to prevent anomalies from developing, a simple insert or update command can still cause data incongruities. 

Less capable of handling diverse and complex queries: Database designers build and optimize star schemas for specific analytical needs. As denormalized data sets, they work best with a relatively narrow set of simple queries. Comparatively, a normalized schema permits a far wider variety of query complexity. 

No many-to-many relationships: Because they offer a single-dimension schema, star schemas don’t work well for “many-to-many data relationships.”