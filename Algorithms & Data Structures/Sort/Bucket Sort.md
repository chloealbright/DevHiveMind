---
tags:
  - sortAlgo
author:
  - jacgit18
Status: init
Started: 
EditDate: 
Relates:
---
![[unnamed (14).gif]]

Bucket sort is particularly effective when dealing with uniformly distributed input over a specified range. For example, imagine sorting a large set of floating-point numbers ranging from 0.0 to 1.0, distributed uniformly across this range. 

If we were to employ a comparison-based sorting algorithm, such as Merge Sort, Heap Sort, or Quick Sort, we'd be bound by the lower limit of [[Big O#^64043d | Ω]](n log n), which means they can't perform better than n log n in terms of time complexity.

The challenge with applying counting sort is that it relies on keys as indices, and in this scenario, the keys are floating-point numbers.

To tackle this, we turn to bucket sort. The algorithm can be summarized as follows:

- If we assume inserting elements into a bucket takes` O(1) `time (for example, using a linked list to represent each bucket), then steps 1 and 2 will take `O(n)` time.
- Step 4 also takes `O(n) `time because there are n items across all buckets.
- The critical step to analyze is step 3, which takes `O(n)` time on average when the numbers are uniformly distributed.

For more details and implementation, you can refer to the resources linked below:

[What is Bucket Sort](https://www.educative.io/edpresso/what-is-bucket-sort)

[Bucket Sort Algorithm](https://learnersbucket.com/tutorials/algorithms/bucket-sort-algorithm/)