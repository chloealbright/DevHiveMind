---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Enhanced Object Literals  just shorthand for Object Literals 

Basically an object with multiple properties inside including functions to address things like spaghetti code 

Window.onload doesn't matter just for example 

Window.onload = function (){ 

let name = "tom" 

let belt  = '''black' 

// gets values 

let ninja ={ 

name, belt,  

chop(x){ 

conole.log(`chop    ${x}`) 

} 

} 

conole.log(ninja.chop(5)) 

}