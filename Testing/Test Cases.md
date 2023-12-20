---
tags: 
author:
  - jacgit18
Status: 
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

`Test cases need to consider a variety of conditions that the software will be expected to handle. The test case must be able to comprehensively test the software module with almost all possible combinations of main conditions. To be able to comprehensively test all combinations of conditions, the author must find a way to present these conditions such that it is easy for others to review  also small test cases are much faster than a big test case and just as effective.  

##### Cover a small part of functionality – they need to test a larger part of the system.  

	Test cases often focus on a specific function. Often this function is determined by the internal technical design of the software. Instead, the test cases need to reflect the usage patterns and flows. Every test case should try to cover as much of the flow as reasonably possible – going across technical boundaries of the underlying application.  

##### Test within some type of scope  

	Test cases that are most effective reflect the usage patterns.  

	Try looking for the ‘corner-cases’ or ‘boundary conditions.  

	avoid test case that are dependent on each other  

For multiple cases create truth table to gauge likelihood of multiple cases being true or false at same time



# Types of Cases

Base case  

	is where Recursion ends. 

Boundary case  

	Occurs when one of the inputs is at or just beyond maximum or minimum limits. Example One Boundary analysis can be looking at current value and value before and after 

Corner case  

<mark style="background: #FFF3A3A6;"> A more complex boundary check (a corner is a two-dimensional boundary), for example combining <MIN_INT> and <MAX_INT> in a calculation. </mark>

Occurs outside of normal operating parameters/inputs, specifically when multiple environmental variables or conditions are simultaneously at extreme levels , and the user is put at a corner of the configuration space, even though each parameter is within the specified range for that parameter.<mark style="background: #ABF7F7A6;"> (The "outside normal operating parameters" obviously means something like "outside typical combination of operating parameters", not strictly "outside allowed operating parameters". That is, you're still within the valid parameter space, but near its corner.) 
</mark>


Edge case  

	Occurs at an extreme (maximum or minimum) operating parameter. 

<mark style="background: #FFF3A3A6;">	Edge / Boundary check = The maximum or minimum input that is expected to produce correct output. For example, a function which just adds one to a number will have an operating range from <MIN_INT> to <MAX_INT> - 1, since input smaller than <MIN_INT> can't be provided by the user and output larger than <MAX_INT> won't be useful. </mark>

<mark style="background: #FFF3A3A6;">	An edge case typically involves input values that require special handling in an algorithm behind a computer program. As a measure for validating the behavior of computer programs in such cases, unit tests are usually created; they are testing boundary conditions of an algorithm, function, or method. So practice unit test for edge casing that you can use in an interview when writing out the problem and clearing up the problem  </mark>

Input check   

	Tests the user input, as opposed to some internal data structure or the output of a function. For example, in Bash [ $# -gt 0 ] checks that you got at least one input parameter, which could also be a sanity check for a command like find or mail. 

Sanity check  

	Does this even make sense? For example, if your application only outputs integers, sqrt(-1) and log(-1) are undefined. 

Special case check  

	Non-obvious, non-boundary special values, for example, log(1 + the smallest floating-point number) avoid these cases especially in interview. 

For the Corner, Edge, & Test cases more can be added later.