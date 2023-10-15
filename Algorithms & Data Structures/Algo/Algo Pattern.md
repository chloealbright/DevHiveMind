```javascript
cyclicSort 

const find_missing_number = ([3, 1, 5, 4, 2]) =>{ 

  let idx = 0; 

  const CurrentIndexLength = nums.length; 

  while (idx < CurrentIndexLength){ 

    const currentSubarray = nums[idx]; 

    const decrementedSubarray = currentSubarray -1; 

      if (currentSubarray != nums[decrementedSubarray]){ 

  //swap index 

  [ nums[decrementedSubarray], nums[idx]] 

  = 

  [nums[idx], nums[decrementedSubarray]]; 

    } else{ 

      idx++; 

    } 
  } 
      return nums; 

  }





// two pointer reverse string 

let pointer1 = 0; 
let pointer2 = s.length-1; 

while(pointer1<pointer2){ 
    let temp=s[pointer1]; 

    s[pointer1]=s[pointer2]; 
    s[pointer2]=temp; 
    pointer1++; 
    pointer2--; 
} 

return s;










```

## find Level Averages  High Level

Check root if null 

Initialize result array 

Store root in queue = [root]  

Iterate through the queue.length while > 0  

Initialize Sum with 0 

Store queue length 

iterate through scoped size from previous push to queue that increased size of (queue length) for loop 

Store Dequeued Current Node  

add CurrentNode to sum 

check left & right for null push left & right if not equal to null 

push sum / queue CurrentSize after iterating through  queue size 

return result