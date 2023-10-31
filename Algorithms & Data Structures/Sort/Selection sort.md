---
tags:
  - "#WontReallyUse"
  - inPlaceSort
  - sortAlgo
author:
  - jacgit18
Status: done
Started: 
EditDate: 
Relates:
---

![[unnamed (17).gif]]

Selection sort is a simple sorting algorithm. This sorting algorithm is an in-place comparison-based algorithm in which the list is divided into two parts, the sorted part at the left end and the unsorted part at the right end. Initially, the sorted part is empty and the unsorted part is the entire list.  
  
The smallest element is selected from the unsorted array and swapped with the leftmost element, and that element becomes a part of the sorted array. This process continues moving unsorted array boundary by one element to the right.  
  
This algorithm is not suitable for large data sets as its average and worst-case complexities are of Ο(n^2) where n is the number of items. and O(1) for space complexity