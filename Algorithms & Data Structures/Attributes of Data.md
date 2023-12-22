---
tags:
  - CodebaseDecision
  - CodingProblem
author:
  - jacgit18
Status: Refinement
Started: 
EditDate: 
Relates:
---
![[Attributes.gif]]

# What to Think & Ask About

## Analyzing Data Structures/Types/Constructs
- When examining an algorithm, identify the data structures, types, and constructs used.

## Identifying Weak Points
- Understand the potential weaknesses in these data structures.
- Develop an execution plan to address these weaknesses.



## Special String Cases
- Fixed-length alphabet (26 characters)
- Unicode strings with special characters
- Handling a specific set of characters
- Null as an argument
- Non-null terminated C programming language specific

## Special Integer Cases
- 0
- Minimum/maximum integer values
- Negative/Positive integers
- Decimal floor/ceiling

## Array Operations
- Boundary analysis: -1 and 1 after the array length
- Incrementing the entire length of the array
- Handling nested arrays with a single loop
- Min/max considerations
- Splitting an array using binary search
  ```javascript
  const length = array.length;
  const middle = Math.floor(length / 2);
  const left = array.slice(0, middle);
  const right = array.slice(middle);
  ```

## Starting Point and Endpoints
- Considerations for values contained in a specific range
- Length or calculation value
- Reducing iteration by breaking down large ranges
- Decrementing arrays from the end index to the start (array.Length to 0)

## Boundary Analysis
- Analyze the current value in relation to the values before and after.

## Sort Algorithm Boundary Cases
- Potential scenarios where sorting algorithms may fail:
  - Empty input
  - Input with only one element
  - Very long input
  - Garbage inside the collection to be sorted
  - Null input
  - Duplicate elements
  - Collection with all elements equal
  - Odd/even length input

## Understanding Overlapping Cases
- Consider how these boundary cases may overlap or relate to each other.




