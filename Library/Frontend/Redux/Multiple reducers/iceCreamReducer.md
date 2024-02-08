---
tags:
  - web
  - frontend
  - library
  - redux
author:
  - jacgit18
Comments: This documentation is a code snippet showing how reducer manages state change for ice cream actions being dispatch.
Status: Done
Started: 
EditDate: 2024-02-08
Relates:
---
```jsx
import { BUY_ICECREAM } from './iceCreamTypes';

const initialState = {
  numOfIceCreams: 20
};

const iceCreamReducer = (state = initialState, action) => {
  switch (action.type) {
    case BUY_ICECREAM:
      return {
        ...state,
        numOfIceCreams: state.numOfIceCreams - 1
      };
    default:
      return state;
  }
};

export default iceCreamReducer;
```
