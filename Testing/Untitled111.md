---
tags: 
author:
  - jacgit18
Comments: This documentation discusses
Status: Capture
Started: 
EditDate: 
Relates:
---
## Corner case  

A more complex boundary check (a corner is a two-dimensional boundary), for example combining <MIN_INT> and <MAX_INT> in a calculation. 

Occurs outside of normal operating parameters/inputs, specifically when multiple environmental variables or conditions are simultaneously at extreme levels , and the user is put at a corner of the configuration space, even though each parameter is within the specified range for that parameter.

While edge cases occur when only one operating parameter is at an extreme, corner cases occur when multiple parameters are at an extreme. In corner case testing, multiple parameters are tested to identify where issues could arise.

> The "outside normal operating parameters" obviously means something like "outside typical combination of operating parameters", not strictly "outside allowed operating parameters". That is, you're still within the valid parameter space, but near its corner. 



## Edge case  
Edge cases are errors that occur very infrequently. These errors can be as minor as a visual inconsistency or as serious as a total software crash. In order to root out these edge cases before they become an issue, regression testing can be employed to find the source of the problem.


Occurs at an extreme (maximum or minimum) operating parameter. 


Edge / Boundary check = The maximum or minimum input that is expected to produce correct output. For example, a function which just adds one to a number will have an operating range from <MIN_INT> to <MAX_INT> - 1, since input smaller than <MIN_INT> can't be provided by the user and output larger than <MAX_INT> won't be useful. 

An edge case typically involves input values that require special handling in an algorithm behind a computer program. As a measure for validating the behavior of computer programs in such cases, unit tests are usually created; they are testing boundary conditions of an algorithm, function, or method. So practice unit test for edge casing that you can use in an interview when writing out the problem and clearing up the problem  





## Error Guessing

Error guessing is the process by which a developer or tester determines where there may be errors in the software and writes corresponding test cases to address these potential errors so that they may be corrected.


## User Scenario Case Testing

User scenario case testing asks the tester to step into the shoes of the end user. It utilizes actual test cases to ensure that all possible scenarios are addressed. This type of testing focuses on end-to-end scenarios to handle complex problems.

## Decision/ Truth Table Testing

Decision table testing is a form testing that assesses different combinations of inputs and places them in a table. The corresponding outputs are categorized into “true” or “false,” and these are used to determine where there is a problem that needs resolving. 





1. Invalid Input Test Cases:
    
    - These test cases examine how your code handles invalid or unexpected inputs.
    - They help demonstrate your error-handling skills and your code's ability to gracefully handle exceptions.

2. Performance Test Cases:
    
    - In some interviews, performance might be a critical factor.
    - Performance test cases check how your code behaves under certain constraints (e.g., time or space complexity).
    - Relevant for positions where optimizing algorithms is crucial.

3. Stress Test Cases:
    
    - Stress test cases push your code to its limits by providing large or complex inputs.
    - They assess the scalability and efficiency of your solution.
    - Often relevant for roles involving systems or software that need to handle heavy loads.

4. Randomized Test Cases:
    
    - Randomized test cases involve unpredictable input data.
    - They help evaluate your code's correctness and its ability to handle diverse scenarios.
    - Useful for assessing your problem-solving skills in unfamiliar situations.
    
5. Real-World Test Cases:
    
    - Sometimes, interviewers may present scenarios resembling real-world use cases.
    - These assess your ability to translate practical problems into code.
    - Especially important for roles that require understanding and solving real-world issues.




