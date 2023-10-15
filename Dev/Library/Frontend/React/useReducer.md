Use reducer is a hook that is used for state management that is an al 

The diff between the two is usetate is built using uesReducer  

Use reducer is a more primitive hook compared to useState  

Reducer is related to Array.ProtoType.Reduce in javascript  

| JavaScript                                    | React                                                   |
|-----------------------------------------------|---------------------------------------------------------|
| Array.reduce(reducer, intialValue)            | UseReducer(reducer, intialState)                        |
| SingleValue = reducer(accumulator, itemValue) | newState = reducer(currentState, action)                |
| Reduce method returns a single value          | useReducer returns a pair of values[newState, dispatch] |

Use reducer is used for local state inorder to access global state we use it in combination with useContext  

When to use  

UseState should be used when dealing with state that is of type Number, String, or Boolean and the number of state transitions is one or two, when state transitions are unrelated and little to none business logic and dealing with local state 

UseReducer should be used when dealing with state that is of type Object or Array and the number of state transitions is many, when state transitions are related and complex business logic and dealing with global state  

Behaves similar to useState in terms of render behavior  

When you click a button the reducer hooks dispatch function is called which flags to useReducer component for needed updates react traverses component tree to identify flagged components  create element is called then previous render is compared and changes are sent to commit phase  

If you update the state to the same state value after initial render component wont re-render which good especially in the case of a reset button where you have a value of zero & you try to reset the value which is good for performance  

If your updating value after re-renders react just like in useState will re-render one more time then bails out of other re-renders  

Occurs after trigger 

The diff between useState & useReducer is the setState & Dispatcher which use switch statement or alternatives to it