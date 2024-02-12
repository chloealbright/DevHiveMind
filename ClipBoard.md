/**

* @param {number[][]} matrix

* @return {number[]}

*/

function spiralOrder(matrix) {

const result = [];

  

function spiralTraversal(top, bottom, left, right) {

// Traverse top row

for (let i = left; i <= right; i++) {

result.push(matrix[top][i]);

}

  

// Traverse right column

for (let i = top + 1; i <= bottom; i++) {

result.push(matrix[i][right]);

}

  

// Traverse bottom row

if (top < bottom) {

for (let i = right - 1; i >= left; i--) {

result.push(matrix[bottom][i]);

}

}

  

// Traverse left column

if (left < right) {

for (let i = bottom - 1; i > top; i--) {

result.push(matrix[i][left]);

}

}

  

// Move to the inner layer

if (top + 1 <= bottom - 1 && left + 1 <= right - 1) {

spiralTraversal(top + 1, bottom - 1, left + 1, right - 1);

}

}

  

if (matrix.length === 0) {

return result;

}

  

spiralTraversal(0, matrix.length - 1, 0, matrix[0].length - 1);

return result;

}