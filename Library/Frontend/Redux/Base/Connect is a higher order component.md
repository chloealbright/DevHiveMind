---
tags:
  - web
  - frontend
  - library
  - react
  - HOC
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates: "[[Props#Higher Order Components (HOC) and Render Prop Pattern |HOC]]"
---
```javascript
// example

class ClickCounter extends Component {

  

render() {

const { count, incrementCount } = this.props

return <button onClick={incrementCount}>{this.props.name } Clicked {count} times</button>

	}

}

  

export default withCounter(ClickCounter, 5)

  

const withCounter = (WrappedComponent, incrementNumber) => {

class WithCounter extends React.Component {

constructor(props) {

super(props)

  

this.state = {

	count: 0

	}

}

  

incrementCount = () => {

	this.setState(prevState => {

		return { count: prevState.count + incrementNumber }

	})

}

render() {

	console.log('HOC', this.props.name)

	return (

		<WrappedComponent

		count={this.state.count}

		incrementCount={this.incrementCount}

		{...this.props.name}

		// lets you see name in button

		// {...this.props}
		/>

	)}

}

return WithCounter

}

  

export default withCounter
```