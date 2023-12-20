---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Essentially read and write in a sense but with variables instead of DB 

get has no params and just returns something 

set  takes in param and does work but no returns 

const obj = { 

  log: ['a', 'b', 'c'], 

  get latest() { 

    if (this.log.length === 0) { 

      return undefined; 

    } 

    return this.log[this.log.length - 1]; 

  } 

}; 

console.log(obj.latest); 

// expected output: "c" 

const language = { 

  set current(name) { 

    this.log.push(name); 

  }, 

  log: [] 

}; 

language.current = 'EN'; 

language.current = 'FA'; 

console.log(language.log); 

// expected output: Array ["EN", "FA"]



The get syntax binds an object property to a function that will be called when that property is looked up. 

The set syntax binds an object property to a function to be called when there is an attempt to set that property.

look for example