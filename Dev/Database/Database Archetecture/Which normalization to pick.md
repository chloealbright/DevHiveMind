When designing a database schema, it is generally a good idea to aim for a normalization level that is appropriate for the needs of the application.  

It's important to note that aiming for a higher level of normalization may not always be necessary or practical for every application. It depends on the specific needs of the application and the trade-offs between performance, storage efficiency, and maintainability. In some cases, denormalization (i.e. intentionally introducing redundancies) may be appropriate to optimize for certain queries or use cases. 

How would you determine which form is appropriate for your needs 

To determine the appropriate normalization level for a database schema, it's important to consider the specific needs and requirements of the application. Here are a few factors to consider: 

Data integrity: If maintaining the accuracy and consistency of the data is critical for the application, a higher level of normalization may be appropriate. Normalizing the data can help prevent data inconsistencies and reduce the risk of errors. 

Query performance: Normalizing the data can help optimize query performance, especially for applications that require complex queries or need to process large volumes of data. However, denormalizing the data may be necessary for some applications to improve performance. 

Storage efficiency: Normalizing the data can reduce storage requirements and improve storage efficiency, especially for applications that need to store large volumes of data. 

Maintenance and updates: Normalizing the data can make it easier to maintain and update the database schema over time. However, it can also make the schema more complex and harder to understand, which can make maintenance more difficult. 

Business requirements: Ultimately, the normalization level should be driven by the specific business requirements and use cases of the application. For example, if the application requires real-time access to data and needs to support frequent updates, a higher level of normalization may be less appropriate. 

In practice, determining the appropriate normalization level often involves a trade-off between these factors. It's important to consider the specific needs and constraints of the application, and to work with stakeholders to find a solution that meets their needs.