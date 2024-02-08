---
tags:
  - web
  - frontend
  - library
  - react
  - redux
  - hooks
author:
  - jacgit18
Comments: This documentation discusses Redux hooks
Status: Done
Started: 
EditDate: 2024-02-08
Relates: "[[Hooks]]"
---
```JSX
// An alternative approach utilizing Hooks, particularly beneficial when working with Redux Toolkit in conjunction with react-redux for state management.

// This code can be rendered directly in the App component, eliminating the need for connect(mapStateToProps, mapDispatchToProps)(App).

// While the code structure differs, the core concept remains the same.

import { buyCake } from '../redux';

function HooksCakeContainer() {
  const numOfCakes = useSelector(state => state.cake.numOfCakes);
  const dispatch = useDispatch();

  return (
    <div>
      <h2>Number of cakes - {numOfCakes} </h2>
      <button onClick={() => dispatch(buyCake())}>Buy Cake</button>
    </div>
  );
}

export default HooksCakeContainer;
```


