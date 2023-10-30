---
tags:
  - time
  - sortAlgo
  - preProcesing
  - postProcessing
author:
  - jacgit18
Status: refinement
Started: 
EditDate: 
Relates:
---
![[_Images/Algo/GetImage (3).png]]

<iframe src="https://www.hackerearth.com/practice/algorithms/sorting/radix-sort/visualize/" allow="fullscreen" allowfullscreen="" style="height: 100%; width: 100%; aspect-ratio: 4 / 3;"></iframe>
### Merge Sort:

[[Merge sort]]is a reliable sorting algorithm that falls under the category of  `divide and conquer `sorts. It is known for its consistent and linear time complexity.

In the case of Merge Sort, the time complexity is typically `O(n log(n))`. However, Quick Sort can be more space-efficient, but it can have an unfavorable runtime in worst-case scenarios due to its pivot technique, which may lead to `exponential` time complexity.

If you're concerned about worst-case scenarios, Merge Sort is a safer choice. But if you're sorting data in memory on your machine and space efficiency is a priority, Merge Sort can be more resource-intensive. For large data structures, Merge Sort is often a better choice. It's a stable sort and can be adapted for linked lists and large datasets stored on slower media like disks.

### Quick Sort:
[[Quick Sort]] , on the other hand, is known for its space efficiency and good cache locality. It's an in-place sorting algorithm, meaning it doesn't require additional storage space for sorting. In the worst-case scenario, Quick Sort has a time complexity of` O(n^2)`, but this can be improved with techniques like randomized Quick Sort or careful pivot selection.

Quick Sort is particularly efficient for smaller arrays or datasets and has good cache locality, making it faster in some cases, especially in a virtual memory environment.


### Heap Sort
alternatively you can use [[Heap Sort]] but it is a little slower than quicksort but you don't have to worry about worst-case and it has a better space complexity than merge sort 




## Wont Really Use

### [[Bubble sort]] & [[Selection sort]]

Practice with bubble and selection sort to understand basics don't use bubble or selection sort in your code or interview

Bubble insertion and selection sort are typically the worst in terms of runtime which is exponential or `O(n^2) `but when it comes to insertion if best case which is small amounts of data then it can become O(n) or Ω(n) which is linear time


### [[Insertion sort]]

use insertion sort for small inputs that are partially sorted to get the LINEAR TIME `O(n)` and it uses little space  


### [[Bucket Sort]]

Bucket sort is mainly useful when dealing with numbers in different ranges




### [[Radix Sort + Counting Sort]](Not likely to be on interview)

Radix Sort + Counting Sort are used for integers in a restricted range

**In summary:

- Use Merge Sort when reliability and worst-case performance are important, especially for  dealing with larger arrays or datasets.
- Choose Quick Sort when space efficiency and speed for smaller datasets are your priorities.
- Merge Sort is preferred for linked lists and scenarios where stability is crucial.
- Quick Sort is preferred for arrays and can be optimized to be as efficient as Merge Sort in certain cases.
- Both these sorts are usually implement [[Recursion Runtime | Recursively]]

**Sorting Method:**

- Quick sort is considered an internal sorting method, where data is sorted directly in main memory.

- In contrast, merge sort is an external sorting method, typically used when the data to be sorted cannot fit entirely in memory and requires auxiliary storage.

**Stability:**

- Merge sort is a stable sorting method, ensuring that two elements with equal values maintain their original order as they were in the input unsorted array.

- Quicksort, by default, is unstable in this regard but can be modified to achieve stability through code adjustments.

**Preferred For:**

- Quicksort is often the preferred choice for sorting arrays.

- Merge sort, on the other hand, is well-suited for sorting linked lists.