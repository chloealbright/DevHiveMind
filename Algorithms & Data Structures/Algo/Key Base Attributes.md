



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




