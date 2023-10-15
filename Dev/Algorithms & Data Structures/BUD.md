![[_Files/Algo/unnamed 1.gif]]

Bottlenecks 

A brute force algorithm is to go through the array, starting from the first element, and then search through the remaining elements (which will form the other side of the pair). For each pair, compute the difference. If the difference equals k, increment a counter of the difference.  

The bottleneck here is the repeated search for the "other side" of the pair. It's therefore the main thing to focus on optimizing. 

How can we more quickly find the right "other side"? Well, we actually know the other side of ( x,  ? ) .   It's x  +  k or x  -   k. If we sorted the array, we could find the other side for each of the N elements in O( log N)time by doing a binary search. 

We now have a two-step algorithm, where both steps take O(N  log N) time. Now, sorting is the new bottleneck. Optimizing the second step won't help because the first step is slowing us down anyway.  

We just have to get rid of the first step entirely and operate on an unsorted array. How can we find things quickly in an unsorted array? With a hash table.  

Throw everything in the array into the hash table. Then, to look up if x   +    k or x    -k exist in the array, we just look it up in the hash table. We can do this in O(N) time. 

Unnecessary Work 

Get rid of unnecessary work like a condition or a loop especially if it doesn't benefit runtime 

Duplicated Work or DRY Don't Repeat Yourself





