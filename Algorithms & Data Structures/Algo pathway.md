---
tags:
  - codeFlow
  - CodebaseDecision
  - CodingProblem
  - potentialMerge
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates: "[[Linear Iteration vs Linear Recursion  vs Binary Iteration vs Binary Recursion]]"
---
![[paths.gif]]
## Problem Identification

When approaching a problem, it's important to begin by identifying the core issue at hand. Rather than focusing too much on the desired output, consider the attributes and parameters involved, especially when multiple parameters are at play prioritize the parameter that is apart of the main functionality or main problem.

### Handling Numeric Values
![[numbers.png]]
**Numeric values can also be represented with ASCII values
- For an array of numbers or numbers, consider attributes like:
  - Natural numbers (positive and zero)
  - Integers (including natural and negative numbers)
  - Rational numbers (decimal and fraction)
  - Min/Max values
  - Also Pay attention to the number range and order
  - Zero


### Handling String Values
- For strings or arrays of strings, think about the following attributes:
	- is a string empty
	- are there blank spaces
	- string length (odd or even)
	- Substrings like letters in the string
	- Unicode values
	- Unique or specific characters
	- Utilizing built-in string and array functions
	- For arrays of characters, explore algorithm pattern
	- Consider characteristics such as string length, character range, and empty spaces
	- Be cautious with assumptions about ASCII values avoid defaulting to ASCII values.
	- Explore factors like string length(odd/even), character range, and the presence of empty spaces.
	- Evaluate whether you need to traverse every element, which ties back to understanding the problem.
	- Also, think about loop direction (from start or end) and handling duplicates (consider using sets for efficient storage).

## Sorted Data

When data is sorted, focus on binary search, particularly by targeting the middle element.

## Partially Sorted Data

In cases of partial sorting, especially with elements within a specified range, cyclic sort is a valuable approach.

## Unsorted Data

For unsorted data, the choice of algorithm depends on the problem. If preserving order is not a priority, sorting followed by binary search can be effective. Otherwise, consider patterns that might include a linear search.

When working with nested objects like JSON, you often encounter a structure that resembles a tree, involving repetitive tasks such as traversing file directories. In such cases, using recursion can be a powerful technique to efficiently navigate and process these nested structures. Additionally, when you delve deeper into handling repetitive subproblems within these nested structures, you may consider employing memoization techniques to optimize performance and avoid redundant calculations.

## Fixed Length Data

Dealing with data of fixed length, whether it's a matrix or an array, may require approaches like Merge Interval. This can apply to numbers or when handling ASCII values for letters.

- Focus your conditional logic on the fixed length, which is critical for solving these problems.

## Keeping Scope in Mind

It's essential to consider the broader scope of a problem and its impact on the larger context. While precision is valuable for specific tasks, a more generalized approach can provide a broader perspective.

- Precision is useful for specific elements within a scope.
- A more generalized approach allows you to experience the bigger picture.
- Alternating between precision and a broader approach is key; no single tool works for every situation.



