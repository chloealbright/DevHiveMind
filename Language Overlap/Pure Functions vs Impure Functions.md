---
tags:
  - CodebaseDecision
  - MicroCodebaseDecision
  - codeFlow
  - components
author:
  - jacgit18
Status: refinement
Started: 
EditDate: 2023-10-29
Relates:
---
Returns the expected output and runs as expected basically predictable in behavior when process input and return output  

So it allows us to replace the function with output which is known as referential transparency which makes it easy to debug and test  

Takes in at least one param otherwise you just create variable  

No side effects like accessing a variable in the global scope outside of function which makes it impure  

So in order to be pure it cant access DB, API, DataStore, or File System 

also no Modifying DOM or console.log 

no input state  can be modified, no data should be mutated, and input data should be Immutable otherwise avoid mutating it  

Ex: let x = 1                                                                                          

pureIncrement = (num) => num += 1                                                                     

pureIncrement(x) pure because x is,nt mutated 

needs to return something 

Impure harder to test and debug


- **Pure Functional Programming:** Within this, state is not stored, and incoming data is not mutated; you return new data.