---
tags:
  - looping
  - codeFlow
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Pre Increment = (++x) 1 to 10  slightly better the increment operator increments and returns the value after incrementing. 

1, 2, 3, 4, 5 ..., 10 

let a = 2; // 3  

b = ++a; // 3 will log the same because we return after increment not after so no delay 

Post Increment(x++) 1 to 10  the increment operator increments and returns the value before incrementing. 

1+1 = 2,     2+1=3,      3+1 =4   , 4+1 = 5..., 9+1 = 10 

let x = 3; // x = 4 

y = x++; // y = 3  basically x = x +1 gives a slight delay 

if we  log x and  y after initializing them the value of y would be 3 because we return the incremented value before or post its like a delayed response  

Decrementing follows same concept the main difference is when the return happens and with pre(++x) one less step vs post(x++) x = x +1