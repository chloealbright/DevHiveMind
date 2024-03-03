---
tags:
  - codeSnippet
  - twoPointer
  - pattern
author:
  - jacgit18
Comments: This is a coded snippet
Status: Done
Started: 2024-03-03
EditDate: 2024-03-03
Relates:
---
## Attempt
```javascript
function sortArray(nums) {
    let left = 0;
    let right = nums.length - 1;
    let index = 0;

    while (left < right) {
        // Swap if left is greater than or equal to right
        if (nums[left] >= nums[right]) {
            [nums[left], nums[right]] = [nums[right], nums[left]];
            right--;

        } else if (nums[right] > nums[left]) { // This condition seems redundant due to the while loop's logic
            left++;
        }

        // Additional swaps based on the index value
        if (nums[index] > nums[left]) {
            [nums[index], nums[left]] = [nums[left], nums[index]];
        }

        if (nums[index] > nums[right]) {
            [nums[right], nums[index]] = [nums[index], nums[right]];
        }

        index++;
    }
}

```



## Alt Logic
```javascript
function sortColors(nums) {
    let left = 0; // Pointer for 0s
    let right = nums.length - 1; // Pointer for 2s
    let i = 0; // Current element pointer

    while (i <= right) {
        if (nums[i] === 0) {
            // If current element is 0, swap it with the element at the left pointer
            [nums[i], nums[left]] = [nums[left], nums[i]];
            left++; // Move left pointer to the right
            i++; // Move current pointer to the right
        } else if (nums[i] === 2) {
            // If current element is 2, swap it with the element at the right pointer
            [nums[i], nums[right]] = [nums[right], nums[i]];
            right--; // Move right pointer to the left
            // Note: We don't increment i here because the swapped element at index i might be 0 or 1 and needs to be evaluated
        } else {
            // If current element is 1, simply move to the next element
            i++;
        }
    }
}
```


## Explained
Let's simplify this problem and its solution like I'm explaining it to a child, using something familiar, like sorting colored balls.  
  
Imagine you have a line of balls in front of you. These balls are only in three colors: red, white, and blue. Your job is to sort them so that all red balls come first, then all white balls, and blue balls at the end.  
  
You have three baskets in front of you to help with sorting:  
1. The "Red Basket" on your left for red balls.  
2. The "Blue Basket" on your right for blue balls.  
3. You hold the "Sorting Basket" in your hands for white balls, but you don't really need to move white balls; you just leave them in the line as you find them.  
  
Now, you start from the beginning of the line with your Sorting Basket. Here's what you do:  
  
- **When you see a red ball (0):** You swap it with the ball at the position of the Red Basket because you want all red balls to be at the start. Then, you move the Red Basket one step to the right because the next red ball should go next to the one you just moved. You also move one step to the right in the line.  
  
- **When you see a white ball (1):** You don't have to do anything with it; just move one step to the right in the line. White balls are fine where they are because you're moving red and blue balls to their correct places, which automatically sorts the white balls.  
  
- **When you see a blue ball (2):** You swap it with the ball at the position of the Blue Basket because you want all blue balls at the end. Then, you move the Blue Basket one step to the left because the next blue ball should go next to the one you just moved. But, you don't move to the next ball in line yet because the ball you just swapped from the end could be red, and you need to check it and possibly move it to the Red Basket.  
  
You keep doing this until you reach the Blue Basket. At that point, all balls are sorted: red balls are with the Red Basket, white balls are where they were but now correctly in the middle because you've sorted the red and blue balls around them, and blue balls are with the Blue Basket.  
  
The key moments when you move your position in the line (the `i` index) are when you place a red ball in its correct position or when you confirm a ball is white. You don't move forward when you place a blue ball because you need to check the ball you just swapped from the end.