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
```dataview
Table author as Author, ("![|100](" + cover + ")") as Cover, pages, category as genre, rating, Status, File as pdf From "_Pdf/Books Tracker" Where contains(Status, "Unread") 
```

