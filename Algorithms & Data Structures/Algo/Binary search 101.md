## Decisions to considered: 

	Do I use left or right mid? 

	Do I use < or <= , > or >=? 

	How much do I shrink the boundary? is it mid or mid - 1 or even mid + 1 ? 


And just by messing up one of these decisions, either because you don't understand it completely or by mistake, it's going to break your code. 

To solve these decision problems, I use the following set of rules to always keep me away from trouble, most importantly, it makes my code more consistent and predictable in all edge cases. 

### 1) Choice of lo and hi, aka the boundary 

Normally, we set the initial boundary to the number of elements in the array 
```javascript
let lo = 0, hi = nums.length - 1; 
```

But this is not always the case. 

We need to remember: the boundary is the range of elements we will be searching from. 

The initial boundary should include ALL the elements, meaning all the possible answers should be included. Binary search can be applied to none array problems, such as Math, and this statement is still valid. 

For example, In LeetCode 35, the question asks us to find an index to insert into the array. 

It is possible that we insert after the last element of the array, thus the complete range of boundary becomes 
```javascript
let lo = 0, hi = nums.length; 
```
### 2) Calculate mid 

Calculating mid can result in overflow when the numbers are extremely big. I ll demonstrate a few ways of calculating mid from the worst to the best. 
```javascript
let mid = Math.floor((lo + hi) / 2) // worst, very easy to overflow 
let mid = lo + Math.floor((hi - lo) / 2) // much better, but still possible 
let mid = (lo + hi) >>> 1 // the best, but hard to understand 

```
When we are dealing with even elements, it is our choice to pick the left mid or the right mid , and as I be explaining in a later section, a bad choice will lead to an infinity loop. 
```javascript
let mid = lo + Math.floor((hi - lo) / 2) // left/lower mid 
let mid = lo + Math.floor((hi - lo + 1) / 2) // right/upper mid 
```
3. How do we shrink boundary 

I always try to keep the logic as simple as possible, that is a single pair of if...else. But what kind of logic are we using here? My rule of thumb is always use a logic that you can exclude mid. 

Let's see an example: 
```javascript
if (target < nums[mid]) { 

hi = mid - 1 

} else { 

lo = mid;  

} 
```
Here, if the target is less than mid, there's no way mid will be our answer, and we can exclude it very confidently using hi = mid - 1. Otherwise, mid still has the potential to be the target, thus we include it in the boundary lo = mid. 

On the other hand, we can rewrite the logic as: 
```javascript
if (target > nums[mid]) { 

lo = mid + 1; // mid is excluded 

} else { 

hi = mid; // mid is included 

} 
```
4. while loop 

To keep the logic simple, I always use 

while(lo < hi) { ... } 

Why? Because this way, the only condition the loop exits is lo == hi. I know they will be pointing to the same element, and I know that element always exists. 

5. Avoid infinity loop 

Remember I said a bad choice of left or right mid will lead to an infinity loop? Let's tackle this down. 

Example: 
```javascript
let mid = lo + ((hi - lo) / 2); // Bad! We should use right/upper mid! 

if (target < nums[mid]) { 

hi = mid - 1 

} else { 

lo = mid;  

} 
```

Now, imagine when there are only 2 elements left in the boundary. If the logic fell into the else statement, since we are using the left/lower mid, it's simply not doing anything. It just keeps shrinking itself to itself, and the program got stuck. 

We have to keep in mind that, the choice of mid and our shrinking logic has to work together in a way that every time, at least 1 element is excluded. 
```javascript
let mid = lo + ((hi - lo + 1) / 2); // Bad! We should use left/lower mid! 

if (target > nums[mid]) { 

lo = mid + 1; // mid is excluded 

} else { 

hi = mid; // mid is included 

} 
```
So when your binary search is stuck, think of the situation when there are only 2 elements left. Did the boundary shrink correctly? 

My rule of thumb when it comes to binary search: 

Include ALL possible answers when initialize lo & hi 

Don't overflow the mid calculation 

Shrink boundary using a logic that will exclude mid 

Avoid infinity loop by picking the correct mid and shrinking logic 

Always think of the case when there are 2 elements left 
```javascript
var search = function (nums, target) { 

  let lo = 0, 

    hi = nums.length - 1 

  while (lo < hi) { 

    let mid = lo + Math.floor((hi - lo + 1) / 2) 

    if (target < nums[mid]) { 

      hi = mid - 1 

    } else { 

      lo = mid 

    } 

  } 

  return nums[lo] == target ? lo : -1 

}
```