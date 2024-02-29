---
tags:
  - linear
  - dataStructure
author:
  - jacgit18
  - chatgpt
Comments: This documentation discusses the different types of Arrays.
Status: Done
Started: 2024-02-29
EditDate: 
Relates: "[[Arrays]]"
---
1. **1D Array:**
-1         +1  
<mark style="background: #FF5582A6;">-1</mark> <mark style="background: #FFF3A3A6;">0 1 2 3</mark> <mark style="background: #FFB86CA6;">4</mark> 
<mark style="background: #FF5582A6;">ob</mark> 1 2 3 4 <mark style="background: #FFB86CA6;">un</mark> 
   - *Definition:* An array with a single dimension, representing a list of elements.
   - *Example:*
     ```javascript
     let oneDimensional = [1, 2, 3, 4, 5];
     ```

2. **2D Array:**
   - *Definition:* An array with two dimensions, often visualized as a grid or matrix.
   - It's a data structure where each element is an array, and the elements within those arrays are arranged in rows and columns. In a two-dimensional array, you can access elements using two indices, typically denoted as `array[row][column]`.  
   - Two-dimensional arrays are commonly used to represent tabular data, grids, matrices, and similar structured data. They are supported in many programming languages.  
   - *Example:*
     ```javascript
     let twoDimensional = [
       [1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]
     ];
     ```

3. **Nested Array:**
   - *Definition:* An array within an array, creating a hierarchy of dimensions.
   - *Example:*
     ```javascript
     let nestedArray = [1, [2, 3], [4, 5, 6]];
     ```

4. **Matrix:**
   - *Definition:* A specific form of a 2D array where each row has the same number of elements.
   - *Example:*
     ```javascript
     let matrix = [
       [1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]
     ];
     ```

**Structure Differences:**
- **1D Array:** Linear structure, contains a single row of elements.
- **2D Array:** Grid structure, consists of rows and columns forming a matrix.
- **Nested Array:** Hierarchical structure, with arrays embedded within other arrays.
- **Matrix:** A special case of a 2D array where each row has the same length.

Understanding these structures helps in organizing and manipulating data efficiently based on the context and requirements of your application.


