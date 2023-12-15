---
tags: 
author:
  - jacgit18
Status: perpetual
Started: 2023-12-15
EditDate: 
Relates:
---
![[Regimen.gif]]
## Prep  
*Master algorithms to be able to solve within 5 to 15 minute  
>[!note] 
>Look on Glassdoor, and then checking Reddit and Quora you can also check their employees on LinkedIn and see if you have any mutual connections you can try to connect to find out about the type of interview question

1. **Focus on One Problem:**  
- Identify problem area.
- Pick one problem something simple like an array question or something.
- Read problems and break them down to understand don't solve practice doing until you feel comfortable then revisit and solve 
  
2. **Bruteforce Solution:**  
- Come up with a Bruteforce solution to gain insight into the problem's dynamics.  
  
3. **Naive Solution:**  
- Develop a naive solution, distinct from the Bruteforce approach.  
- Space out attempts, allowing time for fresh perspectives.
- The Naive solution can be done Imperatively or Declarative consider doing both ways to see if you can do it.
- Lastly consider runtime complexity and data structures brainstorming thinking about their application in terms of access, searching, insertion, and deletion.  

  
4. **Optimal Solution & Grokking Algorithm Patterns:** 
> ***Consider Pair Programming here or in earlier approach
- Develop a Optimal approach
- Consider experiment with looping iteratively and recursively.  
- Delve into advanced algorithm patterns for solution. 
- Think about what patterns can be used for the problem which can be solved with many different patterns depending on the problem itself.
- Keep in mind that one pattern may be more Optimal then the other.
- Also think about Sorting algorithms, create helper functions for code modularity also naming convention. 




Optimize your algorithm with these tips:

1. **Code Review Perspective:**
   - Review your code as if it's written by someone else, and consider potential mistakes and vulnerabilities.

2. **Error Checks:**
   - Think about potential errors and test your code against various inputs.
   - Comment your intended error checks and mention the need for thorough testing.

3. **Darth Vader Principle:**
   - Assume malicious input; safeguard your code against intentional misuse.

4. **Test Coverage:**
   - Test with various scenarios: no params, 0, undefined, null, large arrays, and asynchronous code.

6. **Recursion and Loops:**
   - Consider recursion nested in loops for certain scenarios. Compare the advantages and disadvantages of recursion and loops, discussing their Big O implications.

7. **Regex and Documentation:**
   - Utilize regex and refer to documentation for method syntax, especially when dealing with complex parameters.

8. **Array Iteration:**
   - Prefer `map` over `forEach` for array operations. Avoid modifying objects directly.

9. **Reverse and Sort:**
   - Be cautious with reversing; consider using `.sort` instead. Limit the use of reverse.

10. **Nested Array/Matrix:**
    - Work efficiently in the outer row loop, optimizing additions.

11. **Object Iteration:**
    - Understand object iteration methods, and consider converting objects to arrays when needed.

12. **Comparison Focus:**
    - When comparing values, focus on specific points, particularly in array and tree problems.

13. **Identify Repetition:**
    - Recognize and eliminate repetition, bottlenecks, and unnecessary work.

14. **Bottleneck Impact:**
    - Prioritize addressing bottlenecks for significant impacts on runtime complexity.

Optimizing for efficiency and considering potential pitfalls will enhance the robustness of your algorithm.