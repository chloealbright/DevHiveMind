---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
You typically have a some uuid that is assigned as primary keys but the table doesn’t necessary need a primary key depending on your table design 

The id can also be incrementing and be a primary key 

autoincrement column need to be a primary key, so if primary function is used, primary keys are transformed in unique index. MySQL don't support autoincrement column without primary key, so multiple queries are generated to create int column, add increments column to composite primary key then modify the column to autoincrement column. 

You can also default the id to random uuid by passing in knex.raw() with random query statement is param  

raw Runs an arbitrary sql query in the schema builder chain. 

Next you can assign foreign keys passing in key name  

By passing in existing table and referencing specific table column in knex.js  you first assign uuid then pass uuid as foreign key with reference as table name.otherTableColumn 

table.uuid("file_id").notNullable() 

table.foreign("file_id").references("file.id") 

[https://www.cockroachlabs.com/blog/common-foreign-key-mistakes/](https://www.cockroachlabs.com/blog/common-foreign-key-mistakes/)  

Foreign

table.foreign(columns, [foreignKeyName])[.onDelete(statement).onUpdate(statement).withKeyName(foreignKeyName).deferrable(type)] 

Adds a foreign key constraint to a table for an existing column using table.foreign(column).references(column) or multiple columns using table.foreign(columns).references(columns).inTable(table). 

A default key name using the columns is used unless foreignKeyName is specified. 

You can also chain onDelete() and/or onUpdate() to set the reference option (RESTRICT, CASCADE, SET NULL, NO ACTION) for the operation. You can also chain withKeyName() to override default key name that is generated from table and column names (result is identical to specifying second parameter to function foreign()). 

Deferrable foreign constraint is supported on Postgres and Oracle and can be set by chaining .deferrable(type) 

Note that using foreign() is the same as column.references(column) but it works for existing columns. 

references# 

column.references(column) 

Sets the "column" that the current column references as a foreign key. "column" can either be "." syntax, or just the column name followed up with a call to inTable to specify the table. 

Enums are good for defining variations of different types like crypto-currencies they are many of them but they are still currencies similar to that is transaction you buy or sell things 

Ex: 

table.enu(transaction _type, ['buy', 'sell']) 

All these columns are typically notNullable or nullable 

column.notNullable() Adds a not null on the current column being created. 

 Column.nullable() Default on column creation, this explicitly sets a field to be nullable. 

Tables by defualt are sorted by pirimary key but using index changes that and indexing speeds up querys 

