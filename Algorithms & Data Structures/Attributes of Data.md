![[_Files/Algo/unnamed (3).gif]]

# What to Think & ask about

Based on the content of the algorithm you can identify what data structures/types/constructs are used.  
  
Then, you try to understand the (possible) weak points of those and try to come up with an execution plan that will make it run in those cases.  
  
String = Empty, Blank Space, Length odd or even, Substring, Unicode Val, Unique or Specific Characters,  
  
Num(has ascii values) = Natural num(pos & 0), Integers(Natural & neg), Rational num(decimal, fraction), Min/Max  
  
## String with some known special cases:  
Alphabet have fixed length which is 26
Empty string  
empty spaces  
Long string  
Unicode string (special characters)  
If limited to a specific set of characters, what happens when some are not in the range  
Odd/even length string  
Null (as argument)  
Non-null terminated C programing language specific  
  
Integer(have ascii values) with known special cases:  
0  
Min/Max Int integer  
Negative/Positive  
decimal floor/ceiling  
  
Array  
boundary is -1 and 1 after array length  
Do we have to increment the entire length of the array  
  
If dealing with a nested array and you don't have to visit all of the indexes you can just use one loop as opposed to nested for loop  
  
min/ max  
// if sorted Split Array in into left-Low and Right-High after finding middle index binary search  
  
  
const length = array.length;  
const middle = Math.floor(length / 2)  
  
you can create a array of left and right based on middle  
  
//if array length is odd  
  
// left-Low has one more value then Right-High  
const left = array.slice(0, middle)  
const right = array.slice(middle)  
  
// Right-High has one more value then left-Low  
const left = array.slice(0, 1 + middle )  
const right = array.slice(middle + 1)  
  
or  
```javascript
check if mid < target val  
and reassign hi to be one less then mid index (mid - 1)  
else lo equal mid index  
  
[-1,0,3,5,9,12], 9)  
search (nums, target)  
lo = 0,  
hi = nums.length-1;  
while (lo < hi)  
let mid = lo + Math.floor((hi - lo + 1) / 2);  
  
if target < nums[mid]  
hi = mid - 1 // index  
else  
lo = mid; // index  
  
return nums[lo]==target?lo:-1;  

```  
  
Starting point endpoints  
Contained in a range of some sort  
Length or some type of calculation value  
When dealing with large ranges think about breaking things down to lower sub ranges to reduce iteration  
decrementing array from end index = array.Length < arrayStart = 0; -index  
  
Boundary analysis  
look at current value and value before and after  
  
Sort algorithm that could fail in the following boundary cases:  
Empty input  
1 element input  
Very long input (maybe of length max(data type used for index))  
Garbage inside the collection that will be sorted  
Null input  
Duplicate elements  
Collection with all elements equal  
Odd/even length input  
  
Then, take all these cases and create a long list trying to understand how they overlap. Ex:  
Empty string case covers the empty collection case  
Null string == null collection  
etc.