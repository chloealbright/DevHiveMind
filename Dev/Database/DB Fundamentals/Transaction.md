https://fauna.com/blog/database-transaction



A transaction is a collection of database operations that are treated as a unit. PostgreSQL guarantees that all the operations within a transaction complete or that none of them complete. This is an important property? It ensures that if something goes wrong in the middle of a transaction, changes made before the point of failure will not be reflected in the database. A transaction usually starts with a BEGIN command and ends with a COMMIT or ROLLBACK (see the next entries). 

A commit marks the successful end of a transaction. When you perform a commit, you are telling PostgreSQL that you have completed a unit of operation and that all the changes that you made to the database should become permanent. 

A rollback marks the unsuccessful end of a transaction. When you roll back a transaction, you are telling PostgreSQL to discard any changes that you have made to the database (since the beginning of the transaction). 

An index is a data structure that a database uses to reduce the amount of time it takes to perform certain operations. An index can also be used to ensure that duplicate values don't appear where they aren't wanted. I'll talk about indexes in Chapter 4, "Query Optimization."


Commit – The action that causes the all of the changes made by a particular transaction to be reliably written to the database files and made visible to other users. 

Concurrency – The property in which two or more computing processes are executing at the same time. 

Connection – The means of communication between a client and a server. A process may have multiple connections opened, each in its own thread, to one or more databases at a time. 

Consistency – The property of a transaction that guarantees that the state of the database both before and after execution of the transaction remains consistent (i.e., free of any data integrity errors) whether or not the transaction commits or is rolled back. 

Cross-compiler – A compiler that runs on a different platform from the one for which it produces object code. Often even the processor architecture/family of the host and target platforms differ. 

Deadlock – A situation in which resources (i.e. locks) are held by two or more connections that are each needed by the other connections so that they are stuck in an infinite wait loop. For example, connection 1 has a lock on table1 and is requesting a lock on table2 that is currently held by connection 2, which is also requesting a lock on table1. Programming practices can be used to prevent deadlocks from occurring. 

Distributed Database – A database in which data is distributed among multiple computers or devices (nodes), allowing multiple computers to simultaneously access data residing on separate nodes. The Internet of Things (IoT) is frequently considered a vast grid of data collection devices, requiring distributed database functionality to manage. 

DLL – Dynamic Link Library. A library of related functions that are not loaded into memory until they are called by the application program. All RDM APIs are contained in DLLs on those operating systems that support them (e.g., MS-Windows). These are sometimes called shared libraries on some systems. 

DML – Database Manipulation Language. In SQL, such statements as UPDATE, INSERT and DELETE are considered DML. 

Durability – The property of a transaction in which the DBMS guarantees that all committed transactions will survive any kind of system failure. 

Dynamic DDL – The ability to change the definition of a database (its schema) after data has been stored in the database without having to take the database off-line or restructure its files. 

Edge Computing -Edge computing refers to the computing infrastructure at the edge of the network, close to the sources of data. Edge computing reduces the communications bandwidth needed between sensors and the datacenter. Databases with tiny footprints e.g RDM are optimized for edge computing. 

Embedded Database – An embedded database is the combination of a database and the database software which typically resides within an application. The database holds information and the software control the database to access or store information. The application software, or the user-interface, then accesses the database and presents that information in a way which is easy for the user to interpret and understand. 

Encryption – The encoding of data so that it cannot be understood by a human reader. This usually requires the use of an encryption key. A common encryption algorithm is called AES, which uses encryption keys of 128, 192 or 256 bits. See Wikipedia  

Fog Computing – An architecture that distributes computing, storage, and networking closer to users, and anywhere along the Cloud-to-Thing continuum. Fog computing is necessary to run IoT, IIoT, 5G and AI applications. 

Geospatial datatypes – Data types which are specifically optimized for storage of geographic coordinate based data. 

Grouped Lock Request – A single operation that requests locks on more than one table or rows at a time. Either all or none of the requested locks will be granted. Issuing a grouped lock request at the beginning of a transaction that includes all of the tables/rows that can potentially be accessed by the transaction guarantees that a deadlock will not occur.



Hash – An indexing method that provides for a fast retrieval (usually in only one additional disk access) of the row that has a matching column value. See Wikipedia  

Hierarchical Model – A special case of a network model database in which each record type can participate only as the member of one set. 

Hot Spot – In a database, a hot spot is a single shared row of a table that is used and updated so often that it creates a performance bottleneck on the system. 

Implicit Locking – Done by SQL to automatically apply the locks needed to safely execute an SQL statement in a multiuser (i.e., shared database) operational environment. 

IMDB – Abbreviation of In-Memory Database 

Index – A separate structure that allows fast access to a table’s rows based on the data values of the columns used in the index. RDM supports two indexing types: hash and b-tree. A SQL key (not foreign key) is implemented using an index. 

In-Memory (Inmemory) – A feature in which the DBMS keeps the entire contents of a database or table available in computer memory at all times while the database is opened. Frequently, in-memory databases are volatile, meaning that they have little or no durability if the computer malfunctions. Durability issues are frequently prioritized below performance, which increases substantially with memory as the storage media. 

In-process – When referring to a DBMS, it is in-process when the DBMS code resides in the process space of the application program that is using it. If the process is single threaded, then this is a single-user usage of the database(s). A process may have multiple threads with individual connections to a shared database, making it a multi-user database. In-process uses Local Procedure Calls (LPC) vs Remote Procedure Calls (RPC) to a database server in a separate process. 

Isolation – The property of a transaction that guarantees that the changes made by a transaction are isolated from the rest of the system until after the transaction has committed. 

Key – A column or columns on which an index is constructed to allow rapid and/or sorted access to a table’s row. 

Little-Endian – The little-endian convention is a type of addressing that refers to the order of data stored in memory. In this convention, the least significant bit (or “littlest” end) is first stored at address 0, and subsequent bits are stored incrementally. 

Little-endian is the opposite of big-endian, which stores the most significant bit first. Because they are opposites, it is difficult to integrate two systems that use different endian conventions.




Local Procedure Call – A software function call to a library function that exists in-process (same computer, same process space). This is in contrast to Remote Procedure Calls (RPC) which are to functions that reside a different process, whether they are the same computer (using interprocess communication) or a remote computer (using networking). Local procedure calls are significantly faster than remote procedure calls, but require computing resources on the local (client) computer. 

Locking – A method for safely protecting objects from being changed by two or more users (processes/threads) at the same time. A write (exclusive) lock allows access from only one user (process/thread) at a time. A read (shared) lock allows read-only access from multiple users (processes/threads). 

Memory Database – A DBMS that keeps the entire contents of a database or table available in computer memory at all times while the database is opened. Frequently, in-memory databases are volatile, meaning that they have little or no durability if the computer malfunctions. Durability issues are frequently prioritized below performance, which increases substantially with memory as the storage media. 

Mirroring – The ability to copy the changes each transaction made to the database from the master database to one or more slave databases so that exact copies of the master database are always available on the slaves.





Modification Stored Procedure – An SQL stored procedure that contains one or more INSERT, UPDATE, and/or DELETE statements. 

Multi-version Concurrency Control (MVCC) – MVCC is a concurrency control method which allows for multiple types of database access to occur simultaneously. RDM implements this through the use of database snapshots. 

Optimizer – A component of the SQL system that estimates the optimum (i.e., fastest) method to access the database data requested is by particular SQL SELECT, UPDATE, or DELETE statement. 

Page Size – The size in bytes of a database page. 

Page – The basic unit of database file input/output. Database files may be organized into a set of fixed-sized pages containing data associated with one or more record occurrences (table rows). 

Positioned Update/Delete – An SQL UPDATE or DELETE statement that modifies the current row of a cursor.





Raima Database Manager is an ACID-compliant embedded database management system designed for use in embedded systems applications. RDM has been designed to utilize multi-core computers, networking, and on-disk or in-memory storage management





Read-only Transaction – A Multi-Version Concurrency Control (MVCC) feature that allows database data to be read by one process without blocking another process’s modification of that same data. Frequently referred to as a “snapshot.” 

Real-time – A real-time environment is one in which specific tasks must be guaranteed to execute within a specified time interval. For a DBMS to be considered truly real-time, it must be able to perform specific database-related tasks in a time that can be deterministically demonstrated—i.e., the worst case execution time can be demonstrated. Because a general-purpose DBMS deals with dynamic data in which the sizes of tables vary over time, and since DBMS response times depend on the amount of data to be processed they cannot be considered real-time. This is true also for RDM. It is real-time friendly, because it is fast, has a small footprint and has features (such as virtual tables and in-memory storage) that allow it to be used in beneficial ways in a real-time application. 

Record Instance/Occurrence – One set of related data field values associated with a specific record type—equivalent to an SQL row. 

Record Type – A collection of closely related data fields—equivalent to an SQL table. Similar to a C struct, a record type is defined by a set of closely related data fields. 

Referential Integrity – A condition in which the foreign key column values in all of the rows in one table have matching rows in the referenced primary key table. Referential integrity is maintained by SQL during the processing of an INSERT and DELETE statement and any UPDATE statement that modifies a foreign or primary key value. 

Scalar Function – Either a built-in SQL function or a user-defined function that returns a single value computed only from the values of any required arguments at the time the function is called. 

Snapshot Isolation – When a snapshot of the database is taken, an instance of the database is frozen and concurrent reads are allowed to occur on that snapshot. Database writes are allowed to continue while reads on the snapshot are happening. 

Stored Procedure – A named and optionally parameterized compiled set of SQL database access statements that can be executed as a unit through a call to the stored procedure. 

Transaction Log – A sequential record of all of the database changes made by each transaction in the order they were issued. The transaction log is used to ensure that a database conforms to the ACID properties. Transaction logs are also used to mirror or replicate data to other databases. 

Transaction – A set of logically related database modifications that is written to the database as a unit. The database changes associated with a given transaction are guaranteed by the DBMS to be written completely to the database; in the event of a system failure, none are written. The state of the database both before and after a transaction will be consistent with its design. 

Transactional File Server (TFS) – An architectural piece of Raima’s RDM system that may be linked in-process with application code or executed separately as a server process. Its responsibility is to perform all of the database file input and output, serving up database pages to the RDM Runtime library as requested, controlling read-only transactions, and committing all transaction change logs to the database. 

Transactional Stored Procedure – A modification stored procedure in which the database changes made by the procedure are encapsulated in its own transaction.