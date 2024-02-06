---
tags:
  - web
  - frontend
  - library
author:
  - jacgit18
Comments: This documentation discusses
Status: Done
Started: 
EditDate: 2024-02-06
Relates: "[[React High Level]]"
---
Before distinguishing between props and state, let's identify their commonalities:

- Both props and state are plain JS objects.
- Changes to either trigger a render update.
- They are deterministic; If your Component generates different outputs for the same combination of props and state then you're doing something wrong. 

### Decision Guide:
> tl;dr: If a Component needs to alter one of its attributes at some point in time, that attribute should be part of its state, otherwise it should just be a prop for that Component. 

#### Props:
A component is unable to modify its props, yet it assumes the responsibility of assembling the props for its child components. 

When it comes to changing props:

- Props can receive an initial value and be modified by the parent component.
- Default values can be set inside the component, but any changes must occur externally.
- Initial values for child component props can be established, and modifications can be made within the child component.

Props essentially serve as a means of conveying data from parent to child, encapsulating information set by the parent component (with optional defaults) that remains immutable within the receiving component.

```javascript
// Example of using props in a child component
const ChildComponent = ({ propValue }) => {
  return <div>{propValue}</div>;
};
```

#### State:

The state is a snapshot with default values at component mount and undergoes mutations over time, primarily triggered by user events. It represents a serializable snapshot of a specific moment.
- Managed internally within the component.
- Mutable and often used for interactivity.
- Should not be altered by parent components.

```javascript
// Example of using state in a functional component
const MyComponent = () => {
  const [count, setCount] = useState(0);

  const updateCount = () => {
    setCount(count + 1);
  };

  return (
    <button onClick={updateCount}>
      Clicked {count} times
    </button>
  );
};
```

#### Changing Props and State:

- Props can be changed by parent components and have initial values.
- State can be changed within the component but not by parent components.

### Keeping Track of Data:

Components can use state to retain information between renderings, sourced from props or hardcoded.

### Best Practices for `setState`:

- Use `setState` instead of direct state mutation to ensure proper re-rendering.
- Avoid synchronous state updates to prevent out-of-sync data.

### Handling `onClick`:

Ensure proper usage of arrow functions for access to the instance's state during `onClick` events.

```javascript
// Example of using arrow function in onClick
<button onClick={() => updateCount()}>Clicked {count} times</button>
```

### Render Method:

Use the `render` method to display dynamic content based on the current state.

```javascript
// Example of rendering based on state
render() {
  return <div>{this.state.count}</div>;
}
```

This refined note provides a comprehensive understanding of the distinctions and best practices related to props and state in React components, including illustrative code snippets.