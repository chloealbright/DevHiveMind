---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
## Variable  

In some situations, we’d like to declare a variable without an initial value while still ensuring that it will only ever be assigned values of a certain type. If left as any, TypeScript won’t be able to protect us from accidentally assigning a variable to an incorrect type that could break our code.  

We can tell TypeScript what type something is or will be by using a type annotation.  

Variables can have type annotations (also known as type declarations) added just after their names. We provide a type annotation by appending a variable with a colon (:) and the type (e.g., number, string, or any).  

let mustBeAString : string;  

mustBeAString = 'Catdog';  

mustBeAString = 1337;  

// Error: Type 'number' is not assignable to type 'string'  

## Parameter Type Annotations 

function triple(value: number) { 

  return value * 3; 

} 

function greetTripled(greeting: string, value: number) { 

  console.log(`${greeting}, ${triple(value)}!`); 

} 

greetTripled('Hiya', 5);


## Array Type Annotations 

let names: string[] = `['Danny', 'Samantha']`; 

An alternative method is to use the Array<T> syntax, where T stands for the type. 

  

let names: Array<string> = ['Danny', 'Samantha']; 

In the code above, the type, T, is string. We won’t use Array<T> syntax in this lesson, but it’s nice to be familiar with it. 

  

As we may expect, we get a type error if we try to assign an array of numbers to a string[] variable: 

  

let names: string[] = [1,2,3]; // Type Error! 

That was just like an assignment error with primitive types. TypeScript arrays, however, can also throw errors when elements of the wrong type are added: 

  

let names: string[] = ['Damien']; 

names.push(666) // Type Error! 

  

// Arrays: 

let bestNumbers: number[] = [7,77,4]; 

let bestLunches: string[] = ['chicken soup', 'non-chicken soup']; 

let bestBreakfasts: string[]= ['scrambled eggs', 'oatmeal', 'tamago kake gohan', 'any kind of soup']; 

let bestBooleans: boolean[] = [true, false]; 

Multi-dimensional Arrays 

So far we’ve looked at string[] arrays, but we could also have arrays that only contain numbers (number[]) or booleans (boolean[]). In fact, we can make arrays of any type whatsoever. We can also declare multidimensional arrays: arrays of arrays (of some type). 
```
let arr: string[][] = [['str1', 'str2'], ['more', 'strings']]; 
```
Think of the string[][] above as short for (string[])[], that is, an array where every element has type string[]. We’ll explore more complex array types in later lessons. 

The empty array ([]) is compatible with any array type: 

let names: string[] = []; // No type errors. 

let numbers: number[] = []; // No type errors. 

names.push('Isabella');   

numbers.push(30); 

// Arrays
```
let bestNumbers: number[] = [7,77,4]; 

let bestLunches: string[] = ['chicken soup', 'non-chicken soup']; 

let bestBreakfasts: string[]= ['fasting', 'oatmeal', 'tamago kake gohan', 'any kind of soup']; 

let bestBooleans: boolean[] = [true, false]; 

// Multidimensional Arrays: 

let bestMealPlan = [bestLunches, bestBreakfasts, ['baked potato', 'mashed potato']]; 

let bestBooleansTwice = [bestBooleans, bestBooleans]; 

let numbersMulti = [ [[1],[2,3]], [[7],bestNumbers] ];
```