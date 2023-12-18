---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
provider store lets you access state > because we pass the store to provider which wraps the app

  

provider connect redux to react so you can manage state

  

You can pass the store to the app as a prop

  

but you don't want to pass your store to the app and all the lower components over and over again that will affect the performance

  

provider makes it so you dont pass the store to the app all time

  

connect is a higher order function that makes component a smart component meaning it is aware of redux state store

  

Hooks are an alternative to connect specifically the ones included in redux and maybe the others