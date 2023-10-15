Calculate 

let mid = (lo + hi) >>> 1 // the best, but hard to understand. Any explanations? 

"x >> 1" is equivalent of "x // 2" which is "floor division". It's very fast because it just shifts the integer by one bit to the right. 

Example: 

"8" in binary is: 

1000 

If I shift it to the right by one bit, it becomes "4" (8 // 2 == 4): 

0100 

You can see that the number got "floor divided".





Bitwise operators 

Bitwise operators treat arguments as 32-bits (zeros & ones) and work on the level of their binary representation. Ex. Decimal number 9 has a binary representation of <mark style="background: #FFF3A3A6;">1001.</mark> Bitwise operators perform their operations on such binary representations, but they return standard JavaScript numerical values. 

Bitwise operators in JavaScript are as follows: 

-   & (AND) 
    
-   | (OR) 
    
-   ^ (XOR) 
    
-   ~ (NOT) 
    
-   << (Left SHIFT) 
    
-   >> (Right SHIFT) 
    
-   >>> (Zero-Fill Right SHIFT) 


BigInt Operators 

Most operators that can be used with the <mark style="background: #FFF3A3A6;">Number</mark> data type will also work with <mark style="background: #FFF3A3A6;">BigInt</mark> values (e.g. arithmetic, comparison, etc.). However, the unsigned right shift <mark style="background: #FFF3A3A6;">>>></mark> operator is an exception and is not supported. Similarly, some operators may have slight differences in behaviour (for example, division with <mark style="background: #FFF3A3A6;">BigInt</mark> will round towards zero).



From <[https://roadmap.sh/javascript](https://roadmap.sh/javascript)>





base 2 focus on base 2 instead of 10 

let say you have 13 and you want it in binary  

16=(2^4)  is greater than 13 so you skip 2^3 * 2 

now we go to the 4th index like an array so it is      

2^3 = 8 which goes in once so 8 modulo 13 leaves 5  (2^2 * 2) 

2^2 = 4 which goes in once so 4 modulo 5 leaves 1 ( 2^1* 2) 

2^1 = 2 which goes in zero times so 2 modulo 1 leaves 1 ( 2^0 =1 * 2) 

2^0 = 1 which goes in once so 1 modulo 1 leaves 0  ( 1 * 2) 

so the binary is 1101 

8 + 4 = 12 + 2 = 14 is over 13 

8 + 4 = 12 + 2(skip) + 1 = 13 

1         1              0                       1 

because   

 2^3(8) goes into 13 and leaves a remainder of 5  binary is 1 

 2^3(4) goes into 5  and leaves a remainder of 1 binary is 1 

 2^1(2) doesn't go into 1 because 2 cant go into 1 so binary is 0 

 2^0(1) goes into 1 since 1 goes into 1  binary is 1 

[https://algodaily.com/lessons/bitwise-operators-and-bit-manipulation-for-interviews](https://algodaily.com/lessons/bitwise-operators-and-bit-manipulation-for-interviews)  

[https://www.purplemath.com/modules/numbbase.htm](https://www.purplemath.com/modules/numbbase.htm)





base 10 this occurs behind the scenes with bit shifting  

123 +39 = 162 

123 binary is 1111011 

39 binary is 100111 

1 + 1 = 2 binary of 2 is 10 

3 binary is 11 

<< this carries one position to the left "&" does this xor helps with simulating the addition 

1111111   

 1111011 

+ 100111 

---------------- 

 1010010 (162) 

the zero is from 2 which is 10 in binary the one moves to the top of the next position 

that becomes 3 binary is 11 

another 2 so 10 and so and so on 

left shift 1010 is now 0100 

one is shifted out the next zero takes a new position then the next one shift the next position and zero shift the third position then a zero is created in the last position




Comma operators 

The comma operator (,) evaluates each of its operands (from left to right) and returns the value of the last operand. This lets you create a compound expression in which multiple expressions are evaluated, with the compound expression's final value being the value of the rightmost of its member expressions. This is commonly used to provide multiple parameters to a for loop. 

let x = 1; 

x = (x++, x); 

console.log(x); 

// expected output: 2 

x = (2, 3); 

console.log(x); 

// expected output: 3



Arguments object 

The arguments object is an Array-like object accessible inside functions that contains the values of the arguments passed to that function, available within all non-arrow functions. You can refer to a function's arguments inside that function by using its arguments object. It has entries for each argument the function was called with, with the first entry's index at 0. But, in modern code, rest parameters should be preferred.





Rest parameters 

The rest parameter syntax allows a function to accept an indefinite number of arguments as an array, providing a way to represent [variadic functions](https://en.wikipedia.org/wiki/Variadic_function) in JavaScript. 

function sum(...theArgs) { 

  let total = 0; 

  for (const arg of theArgs) { 

    total += arg; 

  } 

  return total; 

} 

console.log(sum(1, 2, 3)); 

// expected output: 6 

console.log(sum(1, 2, 3, 4)); 

// expected output: 10







