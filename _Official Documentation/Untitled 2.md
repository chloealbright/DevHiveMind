---
tags:
  - Official-Documentation
author: jacgit18
Status: done
Started: 
EditDate: 
Relates: "[[]]"
---
```html
<body style="margin: 0; overflow: hidden;"> 
<iframe src="" style="width: 100%; height: 100vh; border: none;"></iframe> </body>
```




  
  

Encapusalation/closure



const myrob = () => {

let cache={};

return myrobDP = (nums,i) =>{

// test cases

if(i in cache){

return cache[i];

}

else{

// base case

if(i<0) return 0;

else{

cache[i]=Math.max(myrobDP(nums,i-2)+nums[i],myrobDP(nums,i-1));

return cache[i];

}

}

}

}

  
  

let price = [1,2,3,1];



  
// acts a private method or vairiabe
const myrobObj = myrob();

  

// if this function took a param it would look like this

  

// Closure is used here

// const newFunction = myrob('out'); first param

// console.log(newFunction);

// console.log(newFunction(price,price.length -1)); return function second param

  
  
  

console.log(myrobObj(price,price.length -1)) // using currying here

// newFunction('out')(price,price.length -1) // altertively you can curry like this

  
  

// console.log(rob(price))

  

console.log(`\n ------- Edge Case -------- `);

  

console.log(` Case 01 ${myrobObj(price,price.length -1)}`)

  
  
  

/**

*

*

*

* Optimal Approach

------------------------

Vairiable:

*/