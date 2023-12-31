---
tags: 
author:
  - jacgit18
Status: Capture
Started: 
EditDate: 
Relates:
---
| Table | Column Name | MySQL Type | PG Type | FK | FK table name | Primary | Length | Allow Null | Default | new table name | new column name |  |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| **companies** |  |  |  |  |  |  |  |  |  | **company** |  |  |
|  | company_id | UUID | UUID | 0 |  | 1 |  | N | AUTO |  | id | table.uuid('id').notNullable().primary().defaultTo(knex.raw('(GEN_RANDOM_UUID())')) |
|  | address | LONGTEXT | TEXT | 0 |  | 0 |  | Y | None |  |  | table.text('address') |
|  | is_archive | BOOLEAN | BOOLEAN | 0 |  | 0 |  | Y | FALSE |  |  | table.boolean('is_archive').defaultTo(false) |
|  | file_id | UUID | UUID | 1 | file | 0 |  | N | None |  |  | table.uuid('file_id').notNullable() |
|  | name | VARCHAR | TEXT | 0 |  | 0 | 150 | N | None |  |  | table.text('name').notNullable() |
|  | phone | VARCHAR | TEXT | 0 |  | 0 | 20 | Y | None |  |  | table.text('phone') |
|  | type | ENUM | ENUM | 0 |  | 0 |  | N | None |  | company_type | table.enum('company_type').notNullable() |
|  | created_by | UUID | UUID | 1 | user? | 0 |  | N | None |  |  | table.uuid('created_by').notNullable() |
|  | date_created | DATETIME | TIMESTAMP | 0 |  | 0 |  | N | 0000-00-00 00:00:00 |  |  | table.timestamp('date_created').notNullable() |
|  |  |  |  |  |  |  |  |  |  |  |  |  |
| users |  |  |  |  |  |  |  |  |  | user |  |  |
|  | user_id | UUID | UUID | 0 |  | 1 |  | N | AUTO |  | id | table.uuid('id').notNullable().primary().defaultTo(knex.raw('(GEN_RANDOM_UUID())')) |
|  | is_archive | BOOLEAN | BOOLEAN | 0 |  | 0 |  | Y | FALSE |  |  | table.boolean('is_archive').defaultTo(false) |
|  | email | VARCHAR | TEXT | 0 |  | 0 | 100 | N | None |  |  | table.text('email').notNullable() |
|  | first_name | VARCHAR | TEXT | 0 |  | 0 | 50 | N | None |  |  | table.text('first_name').notNullable() |
|  | last_name | VARCHAR | TEXT | 0 |  | 0 | 50 | N | None |  |  | table.text('last_name').notNullable() |
|  | phone | VARCHAR | TEXT | 0 |  | 0 | 20 | Y | None |  |  | table.text('phone') |
|  | file_id | UUID | UUID | 1 | file | 0 |  | N | None |  |  | table.uuid('file_id').notNullable() |
|  | password | VARCHAR | TEXT | 0 |  | 0 | 100 | N | None |  |  | table.text('password').notNullable() |
|  | date_created | DATETIME | TIMESTAMP | 0 |  | 0 |  | N | 0000-00-00 00:00:00 |  |  | table.timestamp('date_created').notNullable() |
|  | date_modified | DATETIME | TIMESTAMP | 0 |  | 0 |  | N | 0000-00-00 00:00:00 |  |  | table.timestamp('date_modified').notNullable() |
