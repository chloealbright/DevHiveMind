### [[Declarative Coding]] Example

Array has a map method watch out not to confuse with map data structure 

### Convert num to string 
	let num = 24                       
	var str = num.toString(); // '24' now you can use string method 

### Alt length check 
	let myArray = []                                                          
	console.log(myArray?.length ? true : false) 

.trim().split(" ").pop().length;                                                                               
rm white-space at start and end > split by space into array > pop end of and get its length 

### Deep Clone 

const deepClone = (obj) =>{        

if (typeof obj !== "object" || obj === null) return obj         

const newObj = Array.isArray(obj) ? [] : {}        

for(let key in obj){                                                                                                               

const value = obj[key]                                                                                                            

newObj[key] = deepClone(value)                                                                                        
    }                                                                      
   return newObj                                                                                    
                        } 

### Odd Even Check 

const result = (number % 2  === 0)  

? Math.sqrt(num)  

: Math.cbrt(num).toFixed(3)   

// to fixed gives numbers allow after decimal and automatically rounds    

function circumference(r) {                                    

   if (Number.isNaN(Number.parseFloat(r)){                                                                         

   return 0;                                                                                            
         }                                                                                                     
            return parseFloat(r)  ;                                        
             }               

       console.log(circumference('4.567abcdefgh')); // prints  4.567    

### Count Characters 

object can be replaced with map would look like this 

let letterFreqMap = new Map();                 

if (!letterFreqMap.has(currChar))              

 letterFreqMap.set(currChar, 1);          

 letterFreqMap.set(currChar,letterFreqMap.get(currChar) + 1 || 1); 

 letterFreqMap.get(currChar) 

 for min and max 

const charCounter = (characterString) =>{          

    let maxRepeat = 0;                              

     let minRepeat = Infinity;                         

    let letterFreq = {},  uniqueChars = 0;         

   for (let currChar of characterString{                                                                        

   if (!letterFreq[currChar]) {                                                    

          uniqueChars++;                                                                       

          letterFreq[currChar] = 1;                                                                                      

} else { 

letterFreq[currChar]++;                                                       

                      }                                                                                                   

maxRepeat = Math.max(maxRepeat, letterFreq[currChar]); minRepeat = Math.min(minRepeat, letterFreq[currChar]);       

                                              }                                                                                             

 return ['Letter Count: ', letterFreq,`UniqCharacter: ${uniqueChars}, MinRepeatCharacters: ${minRepeat}, MaxRepeatCharacters: ${maxRepeat}`]                                   

                               }                                                       

     console.log(charCounter('cbaebabacd')) 

Letter Count:  { c: 2, b: 3, a: 3, e: 1, d: 1 }                                                              

UniqCharacter: 5, MinRepeatCharacters: 1  

MaxRepeatCharacters: 3 

### Range 

const between = (x, min, max) => {                                                                                                            

return x >= min && x <= max;                                                                    

             } 

const x = 0.002                                                                                                        

     if (between(x, 0.001, 0.009)) {                                                                                  

     // something                                                                           

                                      }   

### Filter By Number 

function filterByNumber(obj) {     

    if (typeof (obj) === null) return true;     

     else return false;     

const number = [1, null, 3, 4, 5, "null", 9 ];     number.filter(filterByNumber).map((x) => x)                                                                                              

String.ToCharArray() equivalent on JavaScript 

"012345"                                                                                                       

 .split('') // Splits into chars, returning ["0", "1", "2", "3", "4", "5"]   

 .join(',') // Joins each char with a comma, returning "0,1,2,3,4,5" 

### Generate Array 

let AlphaBet =  Array(26).fill(0) 

const Row = 9, Col = 9;                                                                                       

const val = 0;                                                                                                           

const boardNestedArray = Array.from(Array(Row), () => Array(Col).fill(val)); 

let arr = [                                                                                                               

[0, 1, 1, 1, 1, 1, 1, 1, 1],                                                                                      

[1, 1, 1, 1, 1, 1, 1, 1, 1],                                                                                                        

[2, 1, 1, 1, 1, 1, 1, 1, 1],                                                                                      

[3, 1, 1, 1, 1, 1, 1, 1, 1],                                                                                             

[4, 1, 1, 1, 1, 1, 1, 1, 1],                                                                                       

[5, 1, 1, 1, 1, 1, 1, 1, 1],                                                                                            

[6, 1, 1, 1, 1, 1, 1, 1, 1],                                                                                                            

[7, 1, 1, 1, 1, 1, 1, 1, 1],                                                                                              

[8, 1, 1, 1, 1, 1, 1, 1, 1]                                                                                                  

] 

 [1, 2, 3, 4, 6, 7, 3, undefined]                                                                                                                

-1(Out of bounds)  0  1  2  3  4  5 6  7(doesn't exist) need to push 

You can't just access column since you would be accessing indexes from multiple array which isn't possible so you have to access both row & column           

matrix[currRow].length) or curCol >= matrix.length                   

 matrix[0][1] row 0 col 1                                                                                       

[ [x, 0 ,x],                                                                                                                  

[x, x, x], ...]                                    

matrix[1][0] row 1 col 0 

 [ [x, x, x],                                                                                                                  

 [0, x, x], ...]        

arr[Row][Column] or just the row arr[0]                                              

Row = arr[Row] 

Column = arr[Row][Column] gives row index and subArray in row or column 

[ 9 rows in total index 0 to 8 

row  

[0], = [0, 1, 1, 1, 1, 1, 1, 1, 1], 

[0][0], = 0 from row 0 

... 

 [8] =  [8, 1, 1, 1, 1, 1, 1, 1, 1] 

] 

col would any index inside row from 0 to array length 

Array() Creates a new Array object. 

var arr = Array.from(Array(10).keys()) // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]                                                           

The Array.from() static method creates a new, shallow-copied Array instance from an array-like or iterable object.