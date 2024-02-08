---
tags:
  - web
  - frontend
  - library
  - react
  - HOC
  - redux
  - javascript
  - typescript
author:
  - jacgit18
Comments: This documentation is a code snippet showing connect higher order component.
Status: Done
Started: 
EditDate: 2024-02-07
Relates: "[[Props#Higher Order Components (HOC) and Render Prop Pattern |HOC]]"
---
```jsx
import React, { Component } from 'react';

const withCounter = (WrappedComponent, incrementNumber) => {
  class WithCounter extends React.Component {
    constructor(props) {
      super(props);
      this.state = {
        count: 0
      };
    }

    incrementCount = () => {
      this.setState(prevState => {
        return { count: prevState.count + incrementNumber };
      });
    }

    render() {
      console.log('HOC', this.props.name);
      return (
        <WrappedComponent
          count={this.state.count}
          incrementCount={this.incrementCount}
          {...this.props.name}
        />
      );
    }
  }

  return WithCounter;
};

class ClickCounter extends Component {
  render() {
    const { count, incrementCount } = this.props;
    return <button onClick={incrementCount}>{this.props.name} Clicked {count} times</button>;
  }
}

export default withCounter(ClickCounter, 5);
```

