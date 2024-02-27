---
tags:
  - javascript
  - typescript
author:
  - jacgit18
Comments: This documentation list JavaScript type conversion.
Status: Done
Started: 
EditDate: 
Relates:
---
| Value           | String conversion | Number conversion | Boolean conversion |
| --------------- | ----------------- | ----------------- | ------------------ |
| 20              | '20'              | 20                | true               |
| '20'            | '20'              | 20                | true               |
| false           | 'false'           | 0                 | false              |
| true            | 'true'            | 1                 | true               |
| 0               | '0'               | 0                 | false              |
| '0'             | '0'               | 0                 | true               |
| NaN             | 'NaN'             | NaN               | false              |
| null            | 'null'            | 0                 | false              |
| undefined       | 'undefined'       | NaN               | false              |
| []              | ''                | 0                 | true               |
| ""              | ""                | 0                 | false              |
| [23]            | '23'              | 23                | true               |
| [10,23]         | '10,23'           | NaN               | true               |
| " "             | ' '               | 0                 | true               |
| ['fun']         | 'fun'             | NaN               | true               |
| ['fun','enjoy'] | 'fun,enjoy'       | NaN               | true               |
| function(){}    | 'function(){}'    | NaN               | true               |
| {}              | '[object Object]' | NaN               | true               |
| Infinity        | 'Infinity'        | Infinity          | true               |
| -Infinity       | '-Infinity'       | -Infinity         | true               |