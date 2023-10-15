![[_Files/Algo/GetImage (3).png]]


Sorting in general Merge & Quicksort(Priority for interview) 

Divide and conquer sorts  

mergesort is more reliable and has linear time   

quicksort has good space complexity but the runtime can hurt you in a worst-case scenario it uses a pivot technique to make a smaller list of the pivot size what can make the runtime exponential 

These sorts are associated with dynamic programming and use recursion and those are merge sort and quick sort the runtime for the merge is O(n log(n)) and the same for quick sort but quicksort can be exponential and the space complexity can be a linearithmic time in the worst case 

you can use heap sort but it is a little slower than quicksort but you don't have to worry about worst-case and it has a better space complexity than merge sort 

use insertion sort for small inputs that are partially sorted to get the LINEAR TIMEO(n) and it uses little space  

Practice with bubble and selection sort to understand basics don't use bubble or selection sort in your code or interview

Bubble insertion and selection sort are typically the worst in terms of runtime which is exponential or O(n^2) but when it comes to insertion if best case which is small amounts of data then it can become O(n) or Ω(n) which is linear time 


Radix Sort + Counting Sort are used for integers in a restricted range


# Edit merge tips  and combine

## Merge sort Tip

Merge sort Used a lot more but should try to use for worst-case  

Merge sort is a sorting technique based on the divide and conquer technique. With worst-case time complexity being Ο(n log n), it is one of the most respected algorithms. 

O(n) for space complexity 

So if you're worried about worst-case scenarios you should use Merge sort. 

But if you want to sort in memory on your machine and you're worried about space complexity merge sort 

is going to be really expensive a userspace complexity of all of that. 

However, if he had huge files that can be sorted in memory so you have external sorting that you need 

maybe like a process outside of memory it's suitable for external sorting then merge sort is good because we won't care  as much about space complexity



Merge sort 

Merge sort is better for large data structures: Mergesort is a stable sort, unlike quicksort and heapsort, and can be easily adapted to operate on linked lists and very large lists stored on slow-to-access media such as disk storage or network attached storage. 

Mergesort uses extra space, quicksort requires little space and exhibits good cache locality. Quick sort is an in-place sorting algorithm. In-place sorting means no additional storage space is needed to perform sorting. Merge sort requires a temporary array to merge the sorted arrays and hence it is not in-place giving Quick sort the advantage of space. 

Worst Cases : The worst case of quicksort O(n2) can be avoided by using randomized quicksort. It can be easily avoided with high probability by choosing the right pivot. Obtaining an average case behavior by choosing right pivot element makes it improvise the performance and becoming as efficient as Merge sort. 

Locality of reference : Quicksort in particular exhibits good cache locality and this makes it faster than merge sort in many cases like in virtual memory environment. 

Efficiency : 

Merge sort is more efficient and works faster than quick sort in case of larger array size or datasets. 

whereas 

Quick sort is more efficient and works faster than merge sort in case of smaller array size or datasets. 

Sorting method : 

The quick sort is internal sorting method where the data is sorted in main memory. 

whereas 

The merge sort is external sorting method in which the data that is to be sorted cannot be accommodated in the memory and needed auxiliary memory for sorting. 

Stability : 

Merge sort is stable as two elements with equal value appear in the same order in sorted output as they were in the input unsorted array. 

whereas 

Quick sort is unstable in this scenario. But it can be made stable using some changes in code. 

Preferred for : 

Quick sort is preferred for arrays. 

whereas 

Merge sort is preferred for linked lists.
