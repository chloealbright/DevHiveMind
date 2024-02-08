---
tags:
  - web
  - frontend
  - library
  - redux
author:
  - jacgit18
Comments: This documentation is a code snippet showing
Status: Done
Started: 
EditDate: 2024-02-08
Relates:
---
```jsx
import { BUY_CAKE } from './cakeTypes';

const initialState = {
  numOfCakes: 10
};

const cakeReducer = (state = initialState, action) => {
  switch (action.type) {
    case BUY_CAKE:
      return {
        ...state,
        numOfCakes: state.numOfCakes - action.payload
      };
    default:
      return state;
  }
};

export default cakeReducer;
```
