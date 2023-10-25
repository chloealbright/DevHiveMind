---
tags:
  - CodebaseDecision
  - time
author: jacgit18
---
![[unnamed (31).gif]]
## Space complexity follows big O rules 

Time complexity is more of a priority in comparison to space complexity because in the real world we value CPU processing more than RAM storage because for the cost to run processes is more than ram because the CPU takes on more load than ram that's why you hear the fan ramp up during the gaming which makes time complexity more of the priority 

Basically, speed over memory 

## What causes Space complexity? 

Storing values in a Variable takes up memory  most primitives (Booleans and numbers) takes up <mark style="background: #FFF3A3A6;">constant space O(1)</mark> I takes up about the same amount of memory 

Like looping over a <mark style="background: #FFF3A3A6;">console log is considered constant time</mark> because you're not storing anything 

Another example is <mark style="background: #FFF3A3A6;">if you are iterating and the variable is increasing in size it's still constant time</mark> because the variable contains a number that's going up not if it was a string instead of a number it would be linear space O(n) 

Strings, arrays, and objects take up linear space O(n) the reason arrays take up linear space it's because it's one of the [[Linear Data Structure]]

so LinkedList stacks and queues may also be the same in terms of runtime

Data Structures 

Function Call 

Allocations