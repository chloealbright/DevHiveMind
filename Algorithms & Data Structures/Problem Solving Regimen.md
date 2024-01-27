---
tags: 
author:
  - jacgit18
Status: Perpetual
Started: 2023-12-15
EditDate: 
Relates: 
Comments: The motivation behind this regimen is basically how I would prepare and practice challenges if I had not done one before and written in a way to avoid anti patterns I fell into.
---
![[Regimen.gif]]
## Prep  
*Master algorithms get to the point were you can solve within 5 to 20 min or show your breath of knowledge within the time-frame of the interview  
>[!note] 
>Look on Glassdoor, and then checking Reddit and Quora you can also check their employees on LinkedIn and see if you have any mutual connections you can try to connect to find out about the type of interview question

1. **Focus on One Problem**: 
	- Identify problem area.
	- Pick one problem something simple like an array question or something.
	- Read problems and break them down to understand, don't solve practice doing this until you feel comfortable then revisit and solve. 
	- Keep in mind when to change [[Approach Pivot |Approach]]
	- ***Consider Pair Programming when you get to the point were your good at implementing Optimal solutions or Naive solutions or once you fill that you have enough repetition***
  
2. [[AlgoFlow#**Brute Force Algorithm** |Bruteforce]] **Solution**:  
	- Come up with a Bruteforce solution to gain insight into the problem's dynamics.  
	- Break the problem down until you understand it think about the [[Algo pathway |Attributes of Data]] being passed.  
  
3. [[AlgoFlow#**Naïve Algorithm** |Naive]] **Solution**:  
	- Develop a naive solution, distinct from the Bruteforce approach.  
	- Space out attempts, allowing time for fresh perspectives.
	- The Naive solution can be done [[Common Imperative Algorithms |Imperatively]] or [[Common Declarative Algorithms |Declarative]] consider doing both ways to see if you can do it.
	- Also think about [[All Sorts of Sorts |Sorting]] algorithms in terms what can be applied, you don't necessarily need write one but you can use a pre-made sorting algorithm.
	- Lastly consider runtime complexity and data structures brainstorming thinking about their application in terms of access, searching, insertion, and deletion both [[Linear Data Structure Runtime Comparison |Linear]] and [[Non-Linear Data Structure Runtime Comparison |Non-Linear]]

  
4. [[AlgoFlow#**Optimal Algorithm** |Optimal]] **Solution & [[Key Base Attributes of  Grokking Algorithm patterns |Grokking Algorithm]] Patterns**:
	- Develop a Optimal approach
	- Consider experiment with looping [[Linear Iteration vs Linear Recursion  vs Binary Iteration vs Binary Recursion |iteratively]] and [[Recursion & Recursion Runtime |recursively]].  
	- Delve into advanced algorithm patterns for solution. 
	- Think about what patterns can be used for the problem which can be solved with many different patterns depending on the problem itself.
	- Keep in mind that one pattern may be more Optimal then the other depending on the specifics of the problem.
	- Create helper functions for code modularity also implementing proper [[Naming Conventions]]. 

## Problem Types to Focus On
When it comes to coding challenges your more often going to be solving or creating some type of function to solve the given problem 80 % of the time vs maybe solving some type of `Object Oriented` problem were you are creating some class with several functions which seems to be rare from my experience so not as high priority so you can probably even do 10 % instead of 20% of these type of problems. Side note Leetcode has some problems where it ask you to implement a heap class and probably other OO questions. Also for overall interview prep you probably should prep by doing 80 % to 70 % coding challenges if your new to the technical interview process then 20% to 30% system design interview prep because from my experience you typically get those interviews from larger companies like a Bloomberg, Spotifty, Google, Direct TV, vs a startup were you may not get this type of interview stage but this may vary depending on the job level your interviewing for also.  


**Object-Oriented (OO) Problems Example (20%):**
1. Design a class hierarchy for a zoo with different animal types.
2. Implement a basic banking system with classes for accounts, transactions, and customers.
3. Create a class for a deck of cards with methods for shuffling and dealing.
4. Design a class structure for a simple 2D game with characters, enemies, and items.
5. Implement a class-based solution for a car rental system with cars, customers, and rentals.

**Function-Based Problems Example (80%):**
1. Write a function to find the factorial of a given number.
2. Implement a function to check if a string is a palindrome.
3. Create a function to find the largest element in an array.
4. Write a function to calculate the nth Fibonacci number.
5. Implement a function to reverse a linked list.
6. Design a function that returns the common elements between two arrays.
7. Create a function to check if a number is prime.
8. Write a function to merge two sorted arrays.
9. Implement a function to validate a Sudoku board.
10. Design a function to calculate the area of different geometric shapes.

This mix allows for practicing both the principles of object-oriented design and the development of algorithmic and logical problem-solving skills through functions.
## Problem Solving Template Tablet Version V1
**Use Microsoft whiteboard and draw on to top of image might be better alternative haven't done anything extensive yet
![[Whiteboard.png]]