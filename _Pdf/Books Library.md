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

```dataview
Table without id  pdf as Name, author as Author, ("![|30](" + cover + ")") as Cover, pages, category as genre, rating, Priority, Read From "_Pdf/Books Tracker" Where contains(Read, true)
```




```dataview
Table tester from outgoing([[Book Dir]])
```