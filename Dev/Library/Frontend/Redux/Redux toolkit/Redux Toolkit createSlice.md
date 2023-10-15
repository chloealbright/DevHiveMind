
allows you to mutate state you dont need to return state

it is kinda of like a combination of action and reducer in one


redux toolkit handles state update in the background
  

also auto creates action creator function 

it also returns main reducer
  

```javascript
const createSlice = require('@reduxjs/toolkit').createSlice

  

const initialState = {

numOfCakes: 20

}

  

const cakeSlice = createSlice({

name: 'cake',

initialState,

reducers: {

ordered: state => {

state.numOfCakes--

},

restocked: (state, action) => {

state.numOfCakes += action.payload

}

}

})

  

module.exports = cakeSlice.reducer

module.exports.cakeActions = cakeSlice.actions
```