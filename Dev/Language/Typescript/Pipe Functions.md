

Composition function right to left inside going outside 

using The reduceRight() method applies a function against an accumulator and each value of the array (from right-to-left) to reduce it to a single value. 

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduceRight 

const comp = (...fns) => val => fns.reduceRight((prev, fn) => fn(prev),val) 

const compRes = comp(multiplyBy5, sub1, add2)(4) // return 25 

Pipe Function left to right from start outside going inside 

to do read left to right we use reduce The reduce() method executes a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value. 

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce 

const pipe = (...fns) => (val) => fns.reduce((prev, fn) => fn(prev), val); 

const pipeRes = pipe(add2, sub1, multiplyBy5)(5) // return 30 

// alt version 

const pipeRes2 = pipe( 

  add2, 

  sub1, 

  multiplyBy5 

)(5);// return 30 

// debug 

pipe = (...functions) => (value) => { 

  debugger; 

  return functions.reduce((currentValue, currentFunction) => { 

    debugger; 

    return currentFunction(currentValue); 

  }, value); 

}; 

// custom pointer free were you do not see the unary param passed between each function 

const divideBy = (divsor, num) => (num) => num /divisor 

const pipeRes3 = pipe( 

  add2, 

  sub1, 

  multiplyBy5, 

x => divideBy(2, x) 

)(5); // return 15 

// curry  

const divBy = (divsor) => (num) => num /divisor 

const divideBy2 = divBy(2) // partially applied param 

const pipeRes4 = pipe( 

  add2, 

  sub1, 

  multiplyBy5, 

divideBy2 

)(5); // return 15 

// count words 

const lorem = "dad ada dij wdwh eicv dsc dacas cscs iihi" 

const splitOnSpace = (string) =>  string.split(' ') 

const count =  (array) =>  array.length 

const wordCount = pipe( 

spiltOnSpace, 

count 

) // 9 

// pipe is reusable  

const egbdf = "Every good boy does fine." 

wordCount(egbdf) // 5 

// combining process using palindrome 

const pal1 = "taco cat" 

const pal2 = "UFO tofu" 

const pal3 = "Dave" 

const spilt = (string) => string.split(' ') 

const join = (string) => string.join('') 

const lower = (string) => string.toLowerCase() 

const reverse = (array) => array.reverse() 

const fwd = pipe( 

splitOnSpace, 

join,  

lower 

) 

const rev = pipe( 

fwd, // nested pipe func 

spilt, 

reverse, 

join,  

) 

fwd(pal1) === rev(pal1) // true 

fwd(pal2) === rev(pal2) // true 

fwd(pal3) === rev(pal3) // false 

// clone approach 1 

const scoreObj = {home: 0, away: 0} 

const shallowClone = (obj) => Array.isArray(obj) ? [...obj] : {...obj} 

const incrementHome = (obj) =>{ 

obj.home += 1 // mutation 

return obj 

} 

const homeScore = pipe( 

shallowClone, 

incrementHome 

// another func ... etc 

) 

homeScore(scoreObj) // home: 1, away: 0} 

scoreObj home: 0, away: 0} 

homeScore(scoreObj) === scoreObj false 

// clone approach 2 easier to debug use curry 

let incrementHomeB = (cloneFn) => (obj) =>{ 

const newObj = cloneFn(obj) 

newObj.home += 1 // mutation 

return newObj 

} 

// creates the partial by applying the first arg in advance 

incrementHomeB = incrementHomeB(shallowClone)  

const homeScoreB = pipe( 

incrementHomeB 

) 

homeScoreB(scoreObj) // home: 1, away: 0} 

scoreObj home: 0, away: 0} 

// clone approach 3 

const incrementHomeC = (obj, cloneFn) =>{ 

const newObj = cloneFn(obj) 

newObj.home += 1 // mutation 

return newObj 

} 

const homeScoreC = pipe( 

x => incrementHomeC(x, shallowClone) 

) 

homeScoreC(scoreObj) // home: 1, away: 0} 

scoreObj home: 0, away: 0} 

Pos Pure function with clear dependencies 

Negative non-unary func in your pipe/ compose chain