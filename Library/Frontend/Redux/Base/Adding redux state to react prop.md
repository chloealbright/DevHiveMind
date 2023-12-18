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
const logger = createLogger()

const rootReducers = combineReducers({requestRobots, searchRobots})

const store = createStore(rootReducers, applyMiddleware(thunkMiddleware, logger))

  

ReactDOM.render(

// provider use react context in the background

<Provider store={store}>

 <App/>

</Provider>, document.getElementById('root'));

  

**APP**

  

// parameter state comes from index.js provider store state(rootReducers)

const mapStateToProps = (state) => {

return {

searchField: state.searchRobots.searchField,

robots: state.requestRobots.robots,

isPending: state.requestRobots.isPending

}

}

  

// dispatch the DOM changes to call an action. note mapStateToProps returns object, mapDispatchToProps returns function

  

// the function returns an object then uses connect to change the data from redecers.

const mapDispatchToProps = (dispatch) => {

return {

onSearchChange: (event) => dispatch(setSearchField(event.target.value)),

onRequestRobots: () => dispatch(requestRobots())

}

}

  

class App extends Component {

componentDidMount() {

this.props.onRequestRobots();

}

  

render() {

const { robots, searchField, onSearchChange, isPending } = this.props;

const filteredRobots = robots.filter(robot => {

return robot.name.toLowerCase().includes(searchField.toLowerCase());

})

return (

<div className='tc'>

<h1 className='f1'>RoboFriends</h1>

<SearchBox searchChange={onSearchChange}/>

<Scroll>

{ isPending ? <h1>Loading</h1> :

<ErrorBoundry>

<CardList robots={filteredRobots} />

</ErrorBoundry>

}

</Scroll>

</div>

);

}

}

  

// action done from mapDispatchToProps will channge state from mapStateToProps

export default connect(mapStateToProps, mapDispatchToProps)(App)
```