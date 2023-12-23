---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
```javascript
// Alternate approach with Hooks

// doesn't vary when working with redux toolkit more of react-redux sharing state with react

  

this would be render in the app component and you can get rid of connect(mapStateToProps, mapDispatchToProps)(App)

  

different code same core concept

  

import { buyCake } from '../redux'

  

function HooksCakeContainer () {

const numOfCakes = useSelector(state => state.cake.numOfCakes)

const dispatch = useDispatch()

return (

<div>

<h2>Number of cakes - {numOfCakes} </h2>

<button onClick={() => dispatch(buyCake())}>Buy Cake</button>

</div>

)

}

  

export default HooksCakeContainer
```