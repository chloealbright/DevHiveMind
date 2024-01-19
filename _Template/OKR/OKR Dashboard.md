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

--- start-multi-column: ID_3l9n
```column-settings
Number of Columns: 2
Largest Column: standard
```

placeholder

--- end-column ---


plaeholder

--- end-multi-column

--- start-multi-column: ID_k0t8
```column-settings
Number of Columns: 3
Largest Column: standard
```


placeholder 

--- end-column ---



placeholder


--- end-column ---

placeholder




--- end-multi-column



```dataviewjs
dv.span("**🏋️ Exercise 🏋️**")

const calendarData = {
    colors: {
        red: ["#ff9e82","#ff7b55","#ff4d1a","#e73400","#bd2a00",]
    },
    entries: []
}

for(let page of dv.pages('"System Design Thought Process Flow"').where(p=>p.EditDate)){
    calendarData.entries.push({
        date: page.file.name,
        intensity: page.EditDate,
        content: await dv.span(`[](${page.file.name})`), //for hover preview
    })
       
}

renderHeatmapCalendar(this.container, calendarData)
```