---
tags: 
author:
  - jacgit18
Status: Capture
Started: 
EditDate: 
Relates:
---
| Table | Column Name | MySQL Type | PG Type | FK | FK table name | Primary | Length | Allow Null | Default |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
|  | is_archive | BOOLEAN | BOOLEAN | 0 |  | 0 |  | Y | FALSE |
|  | file_id | UUID | UUID | 1 | file | 0 |  | N | None |
|  | name | VARCHAR | TEXT | 0 |  | 0 | 150 | N | None |
|  | phone | VARCHAR | TEXT | 0 |  | 0 | 20 | Y | None |
|  | type | ENUM | ENUM | 0 |  | 0 |  | N | None |
|  | created_by | UUID | UUID | 1 | user? | 0 |  | N | None |
|  | date_created | DATETIME | TIMESTAMP | 0 |  | 0 |  | N | 0000-00-00 00:00:00 |
|  |  |  |  |  |  |  |  |  |  |
| users |  |  |  |  |  |  |  |  |  |
|  | user_id | UUID | UUID | 0 |  | 1 |  | N | AUTO |
|  | is_archive | BOOLEAN | BOOLEAN | 0 |  | 0 |  | Y | FALSE |
|  | email | VARCHAR | TEXT | 0 |  | 0 | 100 | N | None |
|  | first_name | VARCHAR | TEXT | 0 |  | 0 | 50 | N | None |
|  | last_name | VARCHAR | TEXT | 0 |  | 0 | 50 | N | None |
|  | phone | VARCHAR | TEXT | 0 |  | 0 | 20 | Y | None |
|  | file_id | UUID | UUID | 1 | file | 0 |  | N | None |
|  | password | VARCHAR | TEXT | 0 |  | 0 | 100 | N | None |
|  | date_created | DATETIME | TIMESTAMP | 0 |  | 0 |  | N | 0000-00-00 00:00:00 |
|  | date_modified | DATETIME | TIMESTAMP | 0 |  | 0 |  | N | 0000-00-00 00:00:00 |




| Table | Column Name | MySQL Type | PG Type | FK | FK table name | Primary | Length | Allow Null | Default |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| **companies** |  |  |  |  |  |  |  |  |  |
|  | company_id | UUID | UUID | 0 |  | 1 |  | N | AUTO |
|  | address | LONGTEXT | TEXT | 0 |  | 0 |  | Y | None |
|  | is_archive | BOOLEAN | BOOLEAN | 0 |  | 0 |  | Y | FALSE |
|  | file_id | UUID | UUID | 1 | file | 0 |  | N | None |
|  | name | VARCHAR | TEXT | 0 |  | 0 | 150 | N | None |
|  | phone | VARCHAR | TEXT | 0 |  | 0 | 20 | Y | None |
|  | type | ENUM | ENUM | 0 |  | 0 |  | N | None |
|  | created_by | UUID | UUID | 1 | user? | 0 |  | N | None |
|  | date_created | DATETIME | TIMESTAMP | 0 |  | 0 |  | N | 0000-00-00 00:00:00 |
|  |  |  |  |  |  |  |  |  |  |

