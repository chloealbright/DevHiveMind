---
tags: 
author:
  - jacgit18
Comments: This documentation discusses
Status: Refinement
Started: 
EditDate: 
Relates:
---
In software engineering, a test case is a specification of the inputs, execution conditions, testing procedure, and expected results that define a single test to be executed to achieve a particular software testing objective, such as to exercise a particular program path or to verify compliance with a specific …   

### In general, you should think about the following types of test cases:  

think about what you should expect for a test and if they expect is needed
#### The normal case:  

Does it generate the correct output for typical inputs? Remember to think about potential issues here.  

For example, because sorting often requires some sort of partitioning, it's reasonable to think that the algorithm might fail on arrays with an odd number of elements since they can't be evenly partitioned. Your test case should list both examples.  

#### The extremes:  

What happens when you pass in an empty array or missing param? Or a very small (one element) array? 

What if you pass in a very large one or certain length?  

Nulls and "illegal" input: It is worthwhile to think about how the code should behave when given illegal input or undefined.  

For example, if you're testing a function to generate the nth Fibonacci number, your test cases should probably include the situation where n is negative.  

#### Strange input:  

The next kind of input sometimes comes up: strange input.  

What happens when you pass in an already sorted array? Or an array that's sorted in reverse order?  

Generating these tests does require knowledge of the function you are writing. If you are unclear as to the constraints, you will need to ask your interviewer about this first.  

### Step 2: Define the expected result   

Walk through your code like you would for a detailed code review. Does the code do what you think it should do?  

Often, the expected result is obvious: the right output. However, in some cases, you might want to validate additional aspects. For instance, if the sort method returns a new sorted copy of the array, you should probably validate that the original array has not been touched. 

#### Case should: 

##### Not be too specific  

Test cases need to consider a variety of conditions that the software will be expected to handle. The test case must be able to comprehensively test the software module with almost all possible combinations of main conditions. To be able to comprehensively test all combinations of conditions, the author must find a way to present these conditions such that it is easy for others to review  also small test cases are much faster than a big test case and just as effective.  

##### Cover a small part of functionality – they need to test a larger part of the system.  

	Test cases often focus on a specific function. Often this function is determined by the internal technical design of the software. Instead, the test cases need to reflect the usage patterns and flows. Every test case should try to cover as much of the flow as reasonably possible – going across technical boundaries of the underlying application.  

##### Test within some type of scope  

	Test cases that are most effective reflect the usage patterns.  

	Try looking for the ‘corner-cases’ or ‘boundary conditions.  

	avoid test case that are dependent on each other  

For multiple cases create truth table to gauge likelihood of multiple cases being true or false at same time



# Types of Cases

## Base case  

is where Recursion ends. 

## Boundary case  

	Occurs when one of the inputs is at or just beyond maximum or minimum limits. Example One Boundary analysis can be looking at current value and value before and after 

## Corner case  

A more complex boundary check (a corner is a two-dimensional boundary), for example combining <MIN_INT> and <MAX_INT> in a calculation. 

Occurs outside of normal operating parameters/inputs, specifically when multiple environmental variables or conditions are simultaneously at extreme levels , and the user is put at a corner of the configuration space, even though each parameter is within the specified range for that parameter.

While edge cases occur when only one operating parameter is at an extreme, corner cases occur when multiple parameters are at an extreme. In corner case testing, multiple parameters are tested to identify where issues could arise.

> The "outside normal operating parameters" obviously means something like "outside typical combination of operating parameters", not strictly "outside allowed operating parameters". That is, you're still within the valid parameter space, but near its corner. 

## Iron Corner Case Testing
Iron corner case testing is also known as boundary value analysis, and it seeks to test cases just outside and just inside edge cases.

## Edge case  
Edge cases are errors that occur very infrequently. These errors can be as minor as a visual inconsistency or as serious as a total software crash. In order to root out these edge cases before they become an issue, regression testing can be employed to find the source of the problem.


Occurs at an extreme (maximum or minimum) operating parameter. 


Edge / Boundary check = The maximum or minimum input that is expected to produce correct output. For example, a function which just adds one to a number will have an operating range from <MIN_INT> to <MAX_INT> - 1, since input smaller than <MIN_INT> can't be provided by the user and output larger than <MAX_INT> won't be useful. 

An edge case typically involves input values that require special handling in an algorithm behind a computer program. As a measure for validating the behavior of computer programs in such cases, unit tests are usually created; they are testing boundary conditions of an algorithm, function, or method. So practice unit test for edge casing that you can use in an interview when writing out the problem and clearing up the problem  

Input check   

	Tests the user input, as opposed to some internal data structure or the output of a function. For example, in Bash [ $# -gt 0 ] checks that you got at least one input parameter, which could also be a sanity check for a command like find or mail. 

Sanity check  

	Does this even make sense? For example, if your application only outputs integers, sqrt(-1) and log(-1) are undefined. 

Special case check  

	Non-obvious, non-boundary special values, for example, log(1 + the smallest floating-point number) avoid these cases especially in interview. 

For the Corner, Edge, & Test cases more can be added later.


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





