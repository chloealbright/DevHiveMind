
<mark style="background: #FFF3A3A6;">**The pattern names are just visual abstraction of the pattern  </mark>

## Conditional Logic 

Using not equal might be better than saying not equal or equal to in conditional statement for problem-solving in code because it's fewer lines of code and conditions but the same result 

Too many conditional statements approach doesn't address test cases very well 

A better approach may bring up a lot of test cases and doesn't addresses them so if you are thinking about a lot of conditional statements your approach might not be the best 

Conditional coding avoid else or else if and to many nested conditions  

always create a condition a to exit at begging of loop or method if variable doesn't meet a certain condition having more than one return is ok to do and can make code more efficient 

if you have a lot of conditions break your code down into helper functions to keep that main condition smaller and more readable 

If using other data structures in problem your conditional statements may end up focusing on that new data structure or both depending on the scenario 

loop through length and doing consecutive action on iteration means another loop that is nested 

Recursion can have multiple base cases, you can take in one param and convert into multiple variables divide and conquer especially tree and may use map 

### Sliding Window can leverage Set or Map or other Data Structures 

input of array or string 

May have target of some sort or a sum which increments and decrements 

WindowSize  or WindowSizeStart and you may check if it is greater than diff between WindowEnd to WindowStart  + 1 

WindowEnd initially at first index and increments 

WindowStart eventually increments after WindowEnd or Sum react a certain threshold then sum may decrement after WindowStart increments 

Iterating by array length  

Then a another nested loop with a condition or some sort like sum being greater than or equal to target 

You may also leverage min and max other Math methods depending on what you're doing 

You may return something like length, minLength, maxLength in terms of window size 

Sliding window( you can either do a nested loop or a loop with a lot of conditions to implement the pattern same for to pointer) or separate loops the iteration decrementing and incrementing at certain points represents the window movement 

	Hints similar to Twopointer 

	if a problem mentions contiguous sub-array or sublist 

	Smallest longest contains 

	Substring subarray 

	Typically we use all of the elements within the sliding window for the problem like too combine things or do some type of action within window range 

	You are typically incrementing or decrementing two values that represent the start and end of a window and storing the initial value at the beginning of a array or string when the window shortens and leaves out that last element 

### Two Pointer can leverage Set or Map or other Data Structures 

Two pointer can be applied to two arrays or strings or a combination of a string and a array or used to find numbers in a range just like Sliding window  

input of array or string 

left and right pointer  

You may also leverage min and max other Math methods depending on what you're doing 

Similar attributes to Sliding window 

Iterate through array with while loop with condition of while left is less then right pointer 

Maybe swap values 

can be applied to inputs of sorted arrays list or matrix use sorts before using pointers 

Two pointer technique is quite similar but we usually compare the value at the two pointers instead of all the elements between the pointers. 

Two-pointers can also have variations like a fast-slow pointer. 

which is very useful when dealing with cyclic Linked Lists or Arrays. 

### Cyclic Sort(you can be looking for missing, duplicate, greater or less then/ or looking for a specific value that is missing) 

while (index < ArrayLength) 

currentSubarray = nums[index] 

decrementedSubarray = currentSubarray -1; 

Swap condition which can vary where your checking if  

currentSubarray !== the value of subarray at the index of that initial max range                                                          

currentSubarray !== the value of subarray -1 at the index of that initial max range                                                          

Swap   [ nums[index], nums[decrementedSubarray]]   =    [nums[decrementedSubarray], nums[index]] 

Else Increment Index to ch 

### Merge Intervals 

Take in one matrix or maybe params that can range like another matrix or value to compare  

The matrix is typically pairs of two and might be unsorted or sorted so you might want to sort intervals if not sorted already or sort by rows 

Possible comparison between two matrix were you want to find the min of a pair and compare to min of other pair or other pairs max to create a new range to add to a new matrix 

might be given a matrix with overlapping intervals, and return an array of the non-overlapping basically merging intervals so find min start and max end to push into empty array  

Create/Store multiple indexes if more than one matrix  

Create/Store you can store matrix row currRow = array[row] then access row col by curr[col] which is equivalent to array[row][col] and can reassign values at indexes with other and slice rows      array.splice(index, 2(num of elements to delete), currRow); 

Iterate/Read checking/looping index value is less then matrix length if matrix one matrix length varies shortest one ends loop 

Create/Store and assign each element in the array row to individual variable with array destruct                                                             
ex: let [eleStart, eleEnd] = matrixOne[index] there might two matrix you do this with so you will have to pairs with a start and end  

check and compare starts to each other or ends or ends to each other ex:        

```javascript
 firstIntStart >= secondIntStart && firstIntStart <= secondIntEnd                
                         // or                                                         
 secondIntStart >= firstIntStart && secondIntStart <= firstIntEnd 
```

Update empty array and push the max between pairs and min between pairs typically max between each start and min of the ends but this can vary 

Then some incrementing conditional logic like maybe checking if the first end is less then second end incrementing first matrix index 

### Subsets/Backtracking 
you can potentially apply binary search or start at certain part of matrix depending on what is being asked to do also can be a function that takes in matrix and contains a nested function that takes in initially row and col values 

when hit recursive calls we always check right first until we hit end of row then we go out of bounds check left hit base case until we hit unvisited position and check previous position before starting with left then right, down, up 

Can use closure to take in matrix with outer function then return inner function  with params of Row Col variables with initial value of zero then Store initial method call in variable with matrix param and call variable 

all unique paths from left root, then right root, then down root, then up root 

right 3 times adding 1 to currRow then we hit last index row = 3 col = 0 and try left subbing 1 from currCol row = 2 col = 0 from last right position 1 time then return zero since visited now were still at last right position so we go down at the last right adding 1 to currCol since at new position we check right again and left and so on while we hit base cases with updated Row and col 

Out of Bounds base case 
```javascript
[currRow][curCol] = typically Binary in value or 0 or 1 

// check if row or col is less then zero essentially negative which is out of bounds  or  curRow greater then the 

maxRowLength(matrix[currRow].length) or curCol >= maxColLength (matrix.length) return 0  
```
Already visited 

```javascript
check if cell(matrix[currCol][currRow] ) === 1 return 0 
```

Reached Target 
```javascript
// check if currRow equal maxRowLength - 1 and currCol equal   maxColLength - 1 return 1 

//Mark coordinate as visited   
matrix[curCol][currRow] = 1; 

Initialize sum of all paths or some other action // 4x4 = 38 

Recursive Traversal calls - it can vary depending on the order of direction you traverse in or where is your start and end point on the matrix is  

sumPaths += traverse(Row+1, Col); //right // 10 paths 

sumPaths += traverse(Row-1, Col); //left  // 9 paths 

sumPaths += traverse(Row, Col+1); //down  // 10 paths 

sumPaths += traverse(Row, Col-1); //up  // 9 paths 

Mark coordinate as unvisited   matrix[curCol][currRow] = 0; 

 return sumPaths; 
```

### Modified Binary Search //need explore inner workings more but understand basic just more practice  

Create/Store Low value with value of 0 and High with value of array.length -1  

Create/Store High with value of array.length -1  

Iterate while Low < High 

Create/Store mid-point with value of     

```javascript
Low +  floor( of High - Low + 1 divided by 2)  

 or                                        

Low +  floor( of High - Low divided by 2)  
```

In the context of merge sort  you would Create/Store mid with value of floor(of array length divide by 2) 

Then Create/Store  Low with value of array.slice (values in range of array start index, to  middle)  

and High with value of array.slice (with just middle) or  

Create/Store Low with value of array.slice (values in range of array start index, to  middle +1) that way high would have 1 more value than low 

and High with value of array.slice (middle + 1)  

Do some type of check when you want to UPDATE High 

Do some type of check when you want to UPDATE LOW 

## Bitwise XOR // Have not done yet 

## Heaps //Data Structure Can be Implemented with array or linked list  

Insert 

```javascript
Push initial node  

On second push check if heap array length greater than 1 Create/Store heap length -1 in current 

Then iterate through current while greater than 1 and heap at index value of floor( of current / 2) greater then heap at current index  

if both true swap current node and heap at index value of floor( of current / 2)  

then update current to the floor( of current / 2) 

Then check loop condition again and repeat 
```

Remove 

```javascript
Object pointer reassignment(i.e Node Pointers) 
```

## Top K Elements pattern 

todo

## Fast & Slow Pointers (Linked List Node pointer Swap) 

Check if head exist return false 

Create/Store linked list HEAD in slowPointer variable 

Create/Store linked list HEAD in fastPointer variable 

iterate while .. 

```javascript
check if  fastPointer or fastPointer.next exist return false 

check if slowPointer equal fastPointer or slowPointer equal fastPointer.next  return true 

Update slowPointer to slowPointer.next 

Update fastPointer to fastPointer.next.next 
```

## In Place Reversal of  Linked List Node 

```javascript
Check head length or value or exist 

Create/Store linked list in CURRENT variable 

Create/Store  null in PREVIOUS variable 

Iterate while current not equal to  null 

Create/Store  current.next in NEXT variable 

Update current.next to previous 

Update previous to current 

Update current to next 

return previous 
```

Printing backward specifically recursively goes all the way to null  if you have print after recursive call when you hit last call you print then go back up the call stack and continue console. which are after recursive call