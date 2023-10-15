![[unnamed (24).gif]]

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