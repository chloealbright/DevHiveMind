---
tags: 
author:
  - jacgit18
Status: Capture
Started: 
EditDate: 
Relates: 
Comments: This documentation discusses
---
```dataview
Table author as Author, ("![|100](" + cover + ")") as Cover, pages, category as genre, rating From "books" Where contains(status, "complete") 
```