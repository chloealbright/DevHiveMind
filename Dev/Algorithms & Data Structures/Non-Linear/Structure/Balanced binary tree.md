![[_Files/Algo/GetImage (10).png]]![[_Files/Algo/GetImage (9).png]]

compare tree min and max height and BFS is the more efficient approach 
```javascript

const isBalanced = (tree) => { 

  return minHeight(tree) >= maxHeight(tree) - 1 ? true : false; 

} 

  function maxHeight(node) { 

    if (node == null) { 

      return 0; 

    } 

    return Math.max(maxHeight(node.left), maxHeight(node.right)) + 1; 

  } 

  function minHeight(node) { 

    if (node == null) { 

      return 0; 

    } 

    return Math.min(minHeight(node.left), minHeight(node.right)) + 1; 

  }
```