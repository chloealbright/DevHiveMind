Popular Used a lot more but be careful with it
![[unnamed (16).gif]]

Quick Sort can be created in different ways just like merge sort is a divide and conquer algorithm. and it is usually the fastest on average but the one downside is that it has some pretty nasty worst-case behaviors.  
  
Quicksort has a better rate of average runtime cases and space complexity than merge sort.  
  
  
You see quicksort uses something called a pivoting technique to break the main list into smaller lists and these smaller lists use the pivoting technique until they are sorted.  
  
we keep breaking things down like a tree. And this is where we divide and conquer comes from. Until we have all the individual lists sorted and we combine them. Now you might have two questions for me looking at this. One is how do we even pick this pivot point. And that is kind of random.  
  
  
So if you have to guarantee no bad data or you can guarantee that the pivot is going to be good then you should be avoiding quicksort.  
  
  
Quicksort is really useful and between quicksort and merge I would say those are the most used sorting algorithms.  
  
You'll notice your two things. One is that quick sorts space complexity really good. not as good as bubble sort or insertion sort or selection sort but it's still better than merge. the worst case is 0(n^2) because of this you really want to make sure that you pick a good pivot for quicksort.  
  
You'll get the better space complexity but the worst case could be bad. So in those cases merge sort might be better if your list was presorted for whatever reason. And in that list, if we pick the pivot to be the first item or the last item then our sorting routine would take a very very long time because again the list will not really be split in half and ideally in a quick sort, you're picking the pivot intelligently based on your list.