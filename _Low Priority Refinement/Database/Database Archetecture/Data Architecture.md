---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
data architecture is often an integration process of the components or systems that likely already exist. 

-   The building design is almost always for a new building being built from scratch. A building architect, therefore, could plan and design entirely based on the new requirements and new materials. A data architect does not have this luxury. They can seldom start from scratch, but need to understand the existing platforms and databases while designing for the future. 
    

Given all these differences, a data architect could still learn from building architects and, in particular, take their top-down approach to improve data architecture design. In many organizations, there has been a lack of systematic, centralized, end-to-end data architecture designs. Below lists some of the main reasons: 

-   A company has multiple IT departments, who work in silos with their own data standards and architecture. 
    
-   The applications and processes are built based on individual business requirements, with no data architecture standards to follow. 
    
-   Data architect has the role of only focusing on a limited number of technical areas and possess limited business knowledge about the data. 
    
-   IT projects are managed without considering data architecture as part of the design phase; data scientists and engineers code their way with no consistent data management process. 
    

With these shortfalls, we often see a company with disjointed data systems and gaps between teams and departments. The disparities lead to the poor performance of the systems with many hand-offs, a long time to troubleshoot when a production data issue arises, a lack of accountability to reach the right solution across systems, and a lack of capability to assess the impact of a change. Lastly, the disjointed systems could cause tremendous effort to analyze and research when migrated or re-engineered to the next-gen platform. 

Given all these, a successful enterprise needs to have a top-down coherent data architecture designed based on the business processes and operations. In particular, just like what a building architect does, an enterprise data architect needs to build a blueprint at the conceptual and logical level first, before applying the technologies to the detailed application designs and implementations. 

1. Conceptual Level Data Architecture Design based on Business Process and Operations 

In modern IT, business processes are supported and driven by data entities, data flows, and business rules applied to the data. A data architect, therefore, needs to have in-depth business knowledge, including Financial, Marketing, Products, and industry-specific expertise of the business processes, such as Health, Insurance, Manufacturers, and Retailers. He or she can then properly build a data blueprint at the enterprise level by designing the data entities and taxonomies that represent each business domain, as well as the data flow underneath the business process. In particular, the following areas need to be considered and planned at this conceptual stage: 

-   The core data entities and data elements such as those about customers, products, sales. 
    
-   The output data needed by the clients and customers. 
    
-   The source data to be gathered and transformed or referenced to produce the output data. 
    
-   Ownership of each data entity and how it should be consumed and distributed based on business use cases. 
    
-   Security policies to be applied to each data entity. 
    
-   The relationships between the data entities, such as reference integrity, business rules, execution sequence. 
    
-   Standard data classification and taxonomy. 
    
-   Standards of data quality, operations, and Service Level Agreements (SLAs). 
    

This conceptual level of design consists of the underlying data entities that support each business function. The blueprint is crucial for the successful design and implementation of Enterprise and System architectures and their future expansions or upgrades. In many organizations, this conceptual design is usually embedded in the business analysis driven by the individual project without guidance from the perspective of enterprise end-to-end solutions and standards. 

2. Logical Level Data Architecture Design 

This level of design is sometimes called data modeling by considering which type of database or data format to use. It connects the business requirements to the underlying technology platforms and systems. However, most organizations have data modeling designed only within a particular database or system, given the siloed role of the data modeler. A successful data architecture should be developed with an integrated approach, by considering the standards applicable to each database or system, and the data flows between these data systems. In particular, the following 5 areas need to be designed in a synergistic way: 

The naming conventions and data integrity 

The naming conventions for data entities and elements should be applied consistently to each database. Also, the integrity between the data source and its references should be enforced if the same data have to reside in multiple databases. Ultimately, these data elements should belong to a data entity in the conceptual design in the data architecture, which can then be updated or modified synergistically and accurately based on business requirements. 

Data archival/retention policies 

The data archival and retention policies are often not considered or established until every late-stage on Production, which caused wasted resources, inconsistent data states across different databases, and poor performance of data queries and updates. To enforce the data integrity, data architects should define the data archival and retention policy in the data architecture based on Operational standards. 

Privacy and security information 

Privacy and security become an essential aspect of the logical database design. While the conceptual design has defined which data component is sensitive information, the logical design should have the confidential information protected in a database with limited access, restricted data replication, particular data type, and secured data flows to protect the information. 

Data Replications 

Data Replication is a critical aspect to consider for three objectives: 1) High availability; 2) Performance to avoid data transferring over the network; 3) De-coupling to minimize the downstream impact. Excessive data replications, however, can lead to confusion, poor data quality, and poor performance. Any data replication should be examined by data architect and applied with principles and disciplines. 

Data Flows and Pipelines 

How data flows between different database systems and applications should be clearly defined at this level. Again, this flow is consistent with the flow illustrated in the business process and data architect conceptual level. Besides, the frequencies of the data ingestion, data transformations in the pipelines, and data access patterns against the output data should be considered in an integrated view in the logical design. For example, if an upstream data source comes in real-time, while a downstream system is mainly used for data access of aggregated information with heavy indexes (e.g., expensive for frequent updates and inserts), a data pipeline needs to be designed in between to optimize the performance. 

3. Data Governance is the Key to the Continous Success of Data Architecture. 

As data architecture reflects and supports the business processes and flow, it is subject to change whenever the business process is changed. As the underlying database system is changed, the data architecture also needs to be adjusted. The data architecture, therefore, is not static but needs to be continuously managed, enhanced, and audited. Data governance, therefore, should be adopted to ensure that enterprise data architecture is designed and implemented correctly as each new project is being kicked off. 

Conclusion 

Within a successful data architecture, a conceptual design based on the business process is the most crucial ingredient, followed by a logical design that emphasizes consistency, integrity, and efficiency across all the databases and data pipelines. Once the data architecture is established, the organization can see what data resides where and ensure that the data is secured, stored efficiently, and processed accurately. Also, when one database or a component is changed, the data architecture can allow the organization to assess the impact quickly and guides all relevant teams on the designs and implementations. Lastly, the data architecture is a live document of the enterprise systems, which is guaranteed to be up-to-date and gives a clear end-to-end picture. In summary, a holistic data architecture that reflects the end-to-end business process and operations is essential for a company to advance quickly and efficiently while undergoing significant changes such as acquisitions, digital transformation, or migration to the next-gen platform.