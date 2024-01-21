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
Table author as Author, pdf, ("![|30](" + cover + ")") as Cover, pages, category as genre, rating, Status From "_Pdf/Books Tracker" Where contains(Status, "Unread") 
```

