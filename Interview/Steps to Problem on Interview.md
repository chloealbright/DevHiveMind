![[unnamed (53).gif]]

// Q&A(Listen/ask) repeat question asked

Talk Big O EXCELLENT -> WORST TIME 
lower EXCELLENT + higher WORST = WORST TIME runtime

O(n) + O(n log(n)) = O(n log(n))  

For Big O complexity, all you care about is the dominant term. n log(n) dominates n so that's the only term that you care about.  

CONSTANT O(1) -> LOGARITHMIC O(log n) -> LINEAR O(n)  

no looping -> binary search or some sort of divide and conquer search or multiplication -> individual loop no nested  

LINEARITITHMIC O(n log(n)) -> QUADRATIC O(n^2) ->  

sorting or searching is involved -> nested loop  

EXPONENTIAL O(2^n) -> CUBIC O(n^3) -> FACTORIAL O(n!)  

recursive calls -> triple nested loop -> factorial like questions  

## Things that increase runtime in a function  
Operations (+, -, *, /)  
Comparisons (<, >, = =)
Looping (for, while)  
Outside Function call (function())  
Recursion Function call  

-> List things in pseudocode/whiteboard talk about things in a high level like iterate through data structure or input then reduce it to lower level syntax and list the steps  

### Name method and variables accordingly  

Think about where would this type of problem solution be applied to in real world to come up with a name or some other arbitrary name based on the scenario you come up with put things into context so you can understand and draw a image to establish better names  

### Come up with naive approach  
establish Data structures needed  
think and talk about how your solution may not work  
debug that approach  

##### Define Edge -> Test cases (try and assume case and think of some logic)  

Think about how would you test define utilization and over-utilization basically how something should be used and shouldn't be used  

identify use cases, situations, and scenario, bounds and constraints, stresses and failures conditions, and set limitations  

-> Identify BUD(Bottleneck, Unnecessary & Duplicate work ) in pseudo-code  

-> Code -> Test -> Identify BUD -> Talk or code paths for optimization after code is working or during and LISTEN  

### In general, you should think about the following types of test cases:  
The normal case: Does it generate the correct output for typical inputs? Remember to think about potential issues here. For example, because sorting often requires some sort of partitioning, it's reasonable to  think that the algorithm might fail on arrays with an odd number of elements since they can't be evenly  partitioned. Your test case should list both examples.  

The extremes: What happens when you pass in an empty array? Or a very small (one element) array? What  

if you pass in a very large one?  

Nulls and "illegal" input: It is worthwhile to think about how the code should behave when given illegal input.

For example, if you're testing a function to generate the nth Fibonacci number, your test cases should probably include the situation where n is negative.  

Strange input: The fourth kind of input sometimes comes up: strange input. 

What happens when you pass in an already sorted array? Or an array that's sorted in reverse order?  

Generating these tests does require knowledge of the function you are writing. If you are unclear as to the   constraints, you will need to ask your interviewer about this first.  

### Step 2: Define the expected result  
Often, the expected result is obvious: the right output. However, in some cases, you might want to validate  

additional aspects. For instance, if the sort method returns a new sorted copy of the array, you should  probably validate that the original array has not been touched.hj