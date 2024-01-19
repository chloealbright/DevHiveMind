---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates: 
Comments: Refining to find optimal order of operations in terms of thought for solving a problem .
---

**Ask Question here

like how often test or edge(extremes) cases will have sorted data if at all

Given variables nums array with length minimum  of 2 and length maximum of 104 
the numbers in the array range from -109 to 109 and this the same for the target
returning one valid output array with maximum length of 2  containing the two indexes of the values  that add up to target  for each case 

**Then verify this is what the question is asking

constraint helps with defining scope limiting in put size 

focus thought on the inputs i there are multiple prioritize the one with most actions like insertion, reads,  searches, and deletion then think about the other parameters or vise versa

when it comes to does parameters overall you can maybe like this ok this is an array of integers so what built in functions can be leverage ok with Math, Array, and Numbers what built in functions make sense here then may think along the lines of data structures 

deepening on the input type this will influence you question and line of thought


List what is being reassign,  added too or remove from or inserted into weather it is a data structure a primitive value  

List [[Algorithm Most Common Built in Functions]] relative to the problem your dealing with 


## After you agree on the problem think is anything required in terms of 

### Insertion 
The best way and average time complexity to Insert is a Linked List when it comes to other data structure there is also stacks and queues that are implemented with a linked list theses structures have a constant time complexity or O(1)  

Maps and graphs also have a constant time complexity 

Then there is binary search tree with a Logarithmic Time complexity or O(log n) same for priority queues and heaps
 
 and lastly array 's with a  linear time or O(n) side note there are also queues and stacks implemented by an array with the same runtime


### Reads & Access(MOST COMMON ACTION)  
The best way and average time complexity when it comes to `READS` which I consider a superset of `access` action because a lot of conditional logic weather within loops or outside of loops are just checking if current value or the entirety of the data structure or primitive value in a variable is a particular type or certain size/length or if some even exist.   

Now when it come to the data structures you can use a set if you want to parse out duplicate values this has a runtime complexity of O(1) or use an arrays which doesn't have that side effect and also has a average O(1) complexity same for any structure implemented with an array

If you have a partial solution but test cases are failing and have a whole bunch of conditional logic probably a good indicator to try another approach

Pre condition 
- Define Overlapping condition that may apply also keep [[Conditional Logic and Operators#Short circuit evaluation |Short Circuit Evaluation]] in mind same for other overlap condition below
- Define Individual conditions or whatever else  condition are needed 

loop condition
- Define Overlapping condition that may apply ...
- Create condition to increment and decrement pointers
- Define Individual conditions or whatever else  condition are needed 

post condition 
- Define Overlapping condition that may apply...
- Define Individual conditions or whatever else  condition are needed 


### Search includes Update & Reads for Overall Algorithm

The best way and average time complexity when it comes to searching is a map/hashtable/hashmap when it comes to unsorted data it is  also sometimes refereed to as a lookup table.

On the opposite side of things if dealing with sorted data binary search is a good solution
or Logarithmic Time complexity or O(log n)

Otherwise use  a set or whatever else data structure since the rest searches at a O(n)


Side note partially sorted data can be be indicator to do cyclic sort if you have a complete range of numbers


### Deletion 

The best way and average time complexity when it comes to deletion is basically the same when it comes to all the data structure it  just depends on the deeper use cases outside of runtime since there all delete at a O(n) runtime


Depending on what your trying to do you might pick a lesser optimal runtime based data structure based on what functionality  you want to utilize


# Approach
### Given Variables  case 1
nums = `[2,7,11,15]` 
Target = `9`
Return = `[0,1]`

### Given Variables  case 2
nums = `[3,2,4]` 
Target = `6`
Return = `[1,2]`


### Given Variables  case 3
nums = `[2,7,11,15]` 
Target = `9`
Return = `[0,1]`


## <mark style="background: #CACFD9A6;">C</mark><mark style="background: #BBFABBA6;">R</mark><mark style="background: #D2B3FFA6;">U</mark><mark style="background: #FF5582A6;">D</mark>
## Steps Naive Attempt 
**can list steps or some mixture of steps and pseudocode 

Two pointer pattern comes to mind also is probably the most optimal solution if data is sorted by default or if not not sorted the most optimal solution may include leveraging a data structure that is good with dealing with unsorted data like Hashtable/Hashtable/Map often refereed to as lookup tables which has a O(1) runtime for each action category but Search being the key Operation 



**Hash Map Approach:**
- **Pros:**
    - Handles unsorted arrays efficiently.
    - Provides a direct lookup for previously seen numbers.
- **Cons:**
    - Requires additional space for the hash map.




Step 1 - check array size if less then 2 if so return empty 

Step 2 - can declare `left` and `right` pointer can be outside the loop or inside in case access to the values outside the loop isnt of concern 

step 3 - traverse array of nums and store current `sum` of left and right pointer and <mark style="background: #BBFABBA6;">compare</mark> to target 


Step 4 - return indexes of values that match target

 
## Read 
use truth table to identify overlap conditions 
🔼 AND 🔽OR

logical implication like `p -> q` from discrete math in the programming context just means if the condition is true then do the action in the if statement body.

| Truth Table |  | 1 | 2 | 3 | 1🔼2🔼3 | 1🔽2🔽3 |  |  |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| statement 1 |  | T | T | T | T | T | Placeholder |  |
| statement 2 |  | T | T | F | F | T | Placeholder |  |
| statement 3 |  | F | F | F | F | F | Placeholder |  |
| **Result** |  |  |  |  | N | P |  |  |
|  |  |  |  |  | Not Likely |  |  |  |
|  |  |  |  |  | Proably |  |  |  |
### Two Pointer or any   Approach break down

Pre condition 
- Define Overlapping condition that may apply also keep Short Circuit Evaluation same for other overlap condition below
- Check size of array 

loop condition
- Define Overlapping condition that may apply ...
- Create condition to increment and decrement pointers
- Define whatever else  condition are needed 

post condition 
- Define Overlapping condition that may apply...


## Update does a Reads and might return boolean 

- Reassign any variable or add to value or remove or add any values to data structure using or call a helper or built  in function 

### Delete 
Delete any value from data structure the essentially falls under 


are there scenario were the array has multiple values that add up to target one potential edge case but not relevant to this problem