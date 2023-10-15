```javascript

intialState = {

countToNothing: 10

}
  

function reducer(state = intialState, **action**){

switch(action.type){

// returns new obj no mutation thus pure function

Changes are only made with pure functions meaning a function that takes in an input and gives an output that is predictable

 case DO_ACTION: return {

...state, // copy state update countToNothing

  countToNothing: state.countToNothing - 1

 }

 default: return state

  
 }

}


combineReducers = redux.combineReducers


// similar structure

function counterReducer(state = intialState, action)

function otherCounterReducer(state = intialState, action)


const rootReducers = combineReducers({

counter: counterReducer,

otherCounter: otherCounterReducer

  

})
```