# sql  
---  
```dataview  
TABLE without ID file.link as "Note Title", file.mday as "Last Modified"  
FROM #sql and #type/note  
WHERE file.name != this.file.name  
SORT file.name asc  
```  
  
## ✅ Tasks  
```tasks  
description includes #tag_name  
sort by start date  
```  
  
## 🧾Daily Log  
```query  
block:(/.*🧾.+#tag_name.*/ OR /.*🧾.+#tag_name.*/)  
```