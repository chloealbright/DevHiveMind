---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates: 
Comments:
---
Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

**Example 1:**

**Input:** nums = [2,7,11,15], target = 9
**Output:** [0,1]
**Explanation:** Because nums[0] + nums[1] == 9, we return [0, 1].

**Example 2:**

**Input:** nums = [3,2,4], target = 6
**Output:** [1,2]

**Example 3:**

**Input:** nums = [3,3], target = 6
**Output:** [0,1]

**Constraints:**

- `2 <= nums.length <= 104`
- `-109 <= nums[i] <= 109`
- `-109 <= target <= 109`
- **Only one valid answer exists.**

Ask Question here and after to verify this is what the question is asking

Given variables nums array with length minimum  of 2 and length maximum of 104 
the numbers in the array range from -109 to 109 and this the same for the target
returning one valid output array with maximum length of 2  containing the two indexes of the values  that add up to target  for each case 

## is anything required in terms of 

### Insertion 
#### best way best average time complexity to 
insert is an array also a stack that is probably implemented by a array or a queue implemented by a link list or using a link list just terms of optimizations around Insertions

or 
### Access(MOST COMMON ACTION)  
#### best way best average time complexity to 
access would be a set if you want to parse out duplicate values, arrays no side effects like the set

or

### Search 
#### best way best average time complexity to 


### Deletion 
#### best way best average time complexity to 



depending on what your trying to do you might pick a lesser optimal runtime based data structure based on what functionality  you want to utilize


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
**can list steps of some mixture of steps or a mixture of steps and psudocode 

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
| statement 3 |  |  |  |  | T | T | Placeholder |  |
| **Result** |  |  |  |  | P | P |  |  |
|  |  |  |  |  | Not Likely |  |  |  |
|  |  |  |  |  | Proably |  |  |  |


Pre condition 
- Overlapping condition 
- check size of array 

loop condition
- Overlapping condition 
- Create condition to increment and decrement pointers

post condition 
- Overlapping condition 


## Update does a Reads and might return boolean 


## Delete or Error Exemption if approach isnt deleting stuff



are there scenario were the array has multiple values that add up to target one potential edge case but not relevant to this problem