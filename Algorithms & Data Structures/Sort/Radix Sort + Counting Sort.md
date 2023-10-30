---
tags: 
author:
  - jacgit18
Status: refinement
Started: 
EditDate: 
Relates:
---
<iframe title="Radix Sort | GeeksforGeeks" src="https://www.youtube.com/embed/nu4gDuFabIM?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>



Sorting time complexity can be Improved when you don't make comparisons.  
  
that is where non-comparison sorts and like counting sort and radix sort come in.  
  
counting sort and radix sort is entirely different way to think about sorting.  
  
With comparison sort, we decided the order of the numbers based on asking the question hey is this element bigger than the one over there. And we just kept doing that every number got compared to each other non-comparison sorting does it a little bit differently.  
  
by following the way numbers and data are stored on our computers in zeros and ones and take advantage of that fact to sort things.  
  
these sorts only work with integers in a restricted range  
  
So if you have only numbers that you want to solve sort and the range of those numbers go from let's  
  
say zero to 100 that is a small range then you would use something like this to make things really fast  
  
but it wouldn't work on any type of data.  
  
It only really works on numbers because of the way numbers are stored in memory.  
  
counting sort and radix sort is only useful for fixed-length integers.  
  
But they are able to beat the speed of O(n log n).  
  
there is also bucket's sort  
  
these three sorts have average cases of O(n + K) and radix O(nK)  
  
  
look at docs for more info on the sort and O(n + K), and O(nK)



Certainly, here's a refined version of your note:

**Improving Sorting Time Complexity without Comparisons**

When it comes to optimizing sorting algorithms, it's possible to enhance time complexity without relying on comparisons. This is where non-comparison sorting methods like counting sort and radix sort come into play.

Counting sort and radix sort offer entirely different approaches to sorting data. Unlike comparison-based sorting, which determines the order of numbers by continuously asking whether one element is greater than another, non-comparison sorting takes a unique route.

These methods leverage the binary representation of numbers in our computer systems, operating with zeros and ones to efficiently organize data. However, it's important to note that these non-comparison sorts are most effective with integers within a limited range.

For example, if you have a set of numbers ranging from zero to 100, a small range, these methods can significantly expedite the sorting process. They are specifically tailored for numeric data due to the way numbers are stored in memory.

Counting sort and radix sort are primarily suitable for fixed-length integers, and they can outperform the typical O(n log n) time complexity of comparison-based sorts. 

Additionally, you may encounter another sorting method called bucket sort. These three sorting techniques – counting sort, radix sort, and bucket sort – all have average time complexities of O(n + K) and O(nK).

For more in-depth information on these sorting algorithms and their specific time complexities, I recommend consulting relevant documentation.