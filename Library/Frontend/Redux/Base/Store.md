---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Store is a read only immutable object that is the one source of Truth describing the whole state of the application/website that takes in the reducer as param.
  

everything is happening on the store because it contains the reducer and when we store.dispatcher() where passing in action which goes through store into reducer