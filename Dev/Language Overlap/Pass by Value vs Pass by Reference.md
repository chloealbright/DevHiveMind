pass by Value primitive types 

let a = 10 

let b = 20 

let c = a 

a 10 

b 20 

c 10  

For variable a we take the value of the thing on the right side which is 10 and set that as the value for a. We then repeat the same thing for b, and c. The reason the variable c has the value of 10 is because the variable a is on the right side of the equal sign which means we get the value of "a" which is 10 and set that to the value of c. 

If we were to modify this code slightly and add 1 to c (c = c + 1) then we would get the following chart. 

a 10 

b 20 

c 11 

pass by reference 

As you can see by modifying c we are not actually changing a in anyway even though c was derived from a. This is because when we set the value of c in the above example we are taking c + 1 which is 11 and setting that to the value of c which has no impact on a. Most likely you are familiar with this behavior, but when we introduce arrays/objects things behave a bit different. 

if value isn't primitive type and is something like an array then your storing a reference to the object which would be a memory address  

let a = 10 

let b = 20 

let c = [1, 2] 

Variable Value     Address   Value 

a 10 

b 20 

c 0x01               0x01     [1,2] 

Arrays and objects require a second table that represents the memory address of that array/object. This memory address is just a code that represents where on your computer the data is stored. The value for that variable is then set to the memory address of the array/object associated with the variable. This is called a reference since the variable c references a place in memory instead of a value. 

let a = 10 

let b = 20 

let c = [1, 2] 

let d = c // d shares the same memory address reference  

Variable Value            Address Value 

a 10 

b 20 

c 0x01 

d 0x01                       0x01   [1,2] 

if you push 3 to d array then you will push to the c array to since they share memory address 

c 0x01                                         [1,2,3] 

d 0x01                       0x01   [1,2,3] 

if we reassign the value of d  to a different array it wont affect c because we are overriding the value of d and setting a new memory address but c memory address remains the same 

c 0x01                                         [1,2,3] 

d 0x02                                   d = [3,4,5] 

Why Identical Arrays Are Not equal 

If you run [1, 2] === [1, 2] you would probably expect the answer to be true but in reality the result is false. This is because whenever you compare variables in JavaScript it checks to see if the value of the variables are identical. 

let a = [1, 2] 

let b = [1, 2] 

console.log(a === b) false 

console.log(a == b) false 

different memory address which is being compared if b = c then would be true 

Variable Value     Address Value 

a 0x01                 0x01 [1,2] 

b 0x02                0x02 [1,2] 

Why Is This Important? 

This is important to understand since when you pass an array or object to a function you are passing that reference which means you can actually modify the array/object from within that function. 

const a = [1, 2] 

function addElement(array, element) { 

  array.push(element) 

} 

addElement(a, 3)//  were basically passing memory address 

console.log(a) // [1, 2, 3] 

if we resign  array in function we create a new reference  so a value wouldn't be affect outside the function 

function addElement(array, element) { 

  array =[element] // new memory address 

return array 

}  

addElement(a, 3) // [3] 

console.log(a) // [1, 2] 

this is why you can push to an array of const because the address is constant but what is stored at the memory address can change