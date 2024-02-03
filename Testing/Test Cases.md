---
tags:
  - testing
author:
  - jacgit18
Comments: This documentation discusses test cases.
Status: Refinement
Started: 
EditDate: 2024-02-03
Relates:
---
In software engineering, a test case is a specification of the inputs, execution conditions, testing procedure, and expected results that define a single test to be executed to achieve a particular software testing objective, such as to exercise a particular program path or to verify compliance with a specific …   

# Test Case Guidelines:

1. **Avoid Over-Specificity:**
   - Ensure test cases are not overly specific to allow testing under various conditions.
   - Comprehensive testing should cover a wide range of scenarios and combinations.

2. **Consider Variability:**
   - Test cases should encompass diverse conditions the software may encounter.
   - Emphasize smaller test cases for efficiency while maintaining effectiveness.

3. **Functional Coverage:**
   - Focus on testing broader system functionality instead of isolated functions.
   - Align test cases with user patterns and workflows, transcending technical design boundaries.

4. **Define Scope:**
   - Establish a clear scope for each test case to maintain relevance.
   - Identify and explore 'corner cases' and 'boundary conditions' within the defined scope.

5. **Independence of Test Cases:**
   - Avoid interdependence between test cases to ensure reliable and standalone evaluations.
   - Enhance modularity by isolating test cases from each other.

6. **Truth Tables for Multiple Cases:**
   - Create truth tables for scenarios involving multiple test cases.
   - Evaluate the likelihood of multiple cases being true or false simultaneously.

These refined guidelines aim to optimize the effectiveness and efficiency of test cases, promoting comprehensive testing while aligning with real-world usage patterns.

# Test Case Considerations:

###  Normal Case:
   - Evaluate correctness for typical inputs and anticipate potential issues.
   - Example: Consider sorting algorithms and potential failure on arrays with an odd number of elements due to partitioning. Include such scenarios in your test case.
#### Base Case:
   - Marks the conclusion of recursion.
#### Input Check:
   - Input check refers to the process of validating and ensuring that the data provided as input to a system or program meets certain criteria or constraints. This helps prevent errors, enhance security, and ensure that the system functions as intended. Input checks typically involve verifying data types, range limits, and format adherence to ensure the reliability and safety of the software.
#### Sanity Check:
   - Evaluates whether a given scenario makes logical sense.
   - Example: Verifying the appropriateness of operations like sqrt(-1) and log(-1) in an application outputting only integers.
### Extremes:
   - Explore scenarios with:
     - Empty arrays or missing parameters.
     - Very small (one element) and very large arrays.
     - Address nulls and handle "illegal" input, defining expected behavior.
   - Example: Test cases for generating the nth Fibonacci number should include situations where n is negative.
#### Boundary Case:
   - Occurs at or just beyond maximum or minimum limits.
   - Example: Analyzing current, preceding, and succeeding values to explore boundary conditions.
#### Iron Corner Case Testing:
   - Also known as boundary value analysis.
   - Focuses on testing cases just outside and just inside edge cases.
#### Edge Case:
   - Errors occurring infrequently, ranging from visual inconsistencies to software crashes.
   - Involves extreme operating parameters, testing the maximum or minimum input for correct output.
   - Important for validating program behavior, often addressed through unit tests.
   - Example: Checking boundary conditions of an algorithm, function, or method.

### Strange Input:
   - Challenge the code with unconventional inputs:
     - Already sorted arrays.
     - Arrays sorted in reverse order.
   - Develop these tests based on your understanding of the function, seeking clarification on constraints if needed.
#### Corner Case:
   - Complex boundary checks involving multiple extreme environmental variables or conditions.
   - Testing scenarios where parameters simultaneously reach extreme levels, identifying potential issues.


## Special Case Check(Normal Case/Strange Input):
   - Addresses non-obvious, non-boundary special values.
   - Example: Handling scenarios like log(1 + the smallest floating-point number), particularly in interviews.


These considerations guide the creation of comprehensive test cases, covering normal, extreme, and unconventional scenarios to ensure robust functionality and identify potential edge cases.
