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
Table author as Author, pdf, ("![|30](" + cover + ")") as Cover, pages, category as genre, rating, Priority, Read From "_Pdf/Books Tracker" Where contains(Read, null)
```

## Completed
```dataview
Table author as Author, pdf, ("![|30](" + cover + ")") as Cover, pages, category as genre, rating, Priority, Read From "_Pdf/Books Tracker" Where contains(Read, true)
```


```dataview
Table tester from "_Pdf/Books/" where file.name.fileExtension == "pdf"

```