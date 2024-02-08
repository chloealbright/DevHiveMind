---
tags:
  - web
  - frontend
  - library
  - redux
  - reduxToolKit
author:
  - jacgit18
Comments: This documentation is a code snippet showing how createSlice empowers you to mutate state without requiring explicit state return.
Status: Done
Started: 
EditDate: 2024-02-08
Relates:
---
```jsx
import { createSlice } from '@reduxjs/toolkit';

const initialState = {
  numOfCakes: 20,
};

const cakeSlice = createSlice({
  name: 'cake',
  initialState,
  reducers: {
    ordered: state => {
      state.numOfCakes--;
    },
    restocked: (state, action) => {
      state.numOfCakes += action.payload;
    },
  },
});

export const { ordered, restocked } = cakeSlice.actions;
export default cakeSlice.reducer;
```

`createSlice` serves as a hybrid of action and reducer, streamlining state updates in the background. Additionally, createSlice automatically generates action creator functions and returns the main reducer."