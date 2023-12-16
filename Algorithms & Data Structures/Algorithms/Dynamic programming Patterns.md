---
tags: 
author:
  - jacgit18
Status: init
Started: 2023-12-09
EditDate: 
Relates:
---
Dynamic programming is a powerful technique used in computer science and mathematics to solve optimization problems by breaking them down into smaller overlapping subproblems. There are several common dynamic programming patterns that are frequently used to design efficient algorithms. Here are some of the key dynamic programming patterns:  
  
1. **Memoization (Top-Down):**  
- In this approach, you solve the problem recursively, but you store the results of subproblems in a data structure (usually a dictionary or an array) to avoid redundant computations.  
  
2. **Tabulation (Bottom-Up):**  
- This involves solving the problem iteratively, starting from the smallest subproblems and building up to the larger problem. Results are stored in a table (usually a 1D or 2D array).  
  
3. **1D Dynamic Programming:**  
- This pattern involves using a 1D array to store solutions to subproblems. It is often used when the optimal solution to a problem can be expressed in terms of solutions to smaller subproblems.  
  
4. **2D Dynamic Programming:**  
- Similar to 1D dynamic programming, but uses a 2D array to store solutions. This is common when you need to keep track of two changing parameters or indices.  
  
5. **State Compression:**  
- If the state space in a dynamic programming problem is too large, you can use state compression techniques to reduce memory usage. This involves using a more compact representation of states.  
  
6. **Subset Sum Pattern:**  
- Often used in problems where you need to determine if there exists a subset of elements that satisfies a certain condition (e.g., sum of elements equals a target value).  
  
7. **Knapsack Pattern:**  
- Used in problems where you need to optimize the use of limited resources to maximize or minimize a certain value, such as the classic 0/1 Knapsack problem.  
  
8. **Longest Increasing Subsequence (LIS):**  
- This pattern is used in problems where you need to find the longest increasing subsequence in a given sequence of elements.  
  
9. **Matrix Chain Multiplication:**  
- Applied to problems where you need to find the most efficient way to multiply a chain of matrices.  
  
10. **Edit Distance (Levenshtein Distance):**  
- Commonly used in problems where you need to find the minimum number of edits (insertions, deletions, or substitutions) required to transform one string into another.  
  
These patterns serve as general templates for solving specific types of problems using dynamic programming techniques. When faced with a new problem, recognizing which pattern or combination of patterns to apply can significantly simplify the solution process.