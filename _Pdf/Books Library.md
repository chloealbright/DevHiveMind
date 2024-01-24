---
tags: 
author:
  - jacgit18
Status: Capture
Started: 
EditDate: 
Relates: 
Comments:
---
## To Read
```dataview
Table without id  pdf as Name, author as Author, ("![|30](" + cover + ")") as Cover, pages, category as genre, rating, Priority, Read From "_Pdf/Books Tracker" Where contains(Read, null)
```

## Completed

```dataviewjs
dv.table(
  dv.header("pdf", "Name"),
  dv.header("author", "Author"),
  dv.header('("![|30](" + cover + ")")', "Cover"),
  dv.header("pages", "Pages"),
  dv.header("category", "Genre"),
  dv.header("rating", "Rating"),
  dv.header("Priority"),
  dv.header("Read")
)
  .from("_Pdf/Books Tracker")
  .where("contains(Read, true)");

```



```dataview
Table
from [[Your New Filename.pdf]]
where contains(Published)

```






```dataview
Table tester from outgoing([[Book Dir]])
```