+++
title = "Component State"
description = ""
weight = 23
+++

## initializing State
```js
constructor(props) {
		super(props);
		this.state = {
			comment: "Initial Comment"
		};
	}
```

## Using State Correctly
The only place where you can assign this.state is the constructor.</br>

Do Not Modify State Directly, this will not re-render a component:
{{% alert theme="danger" %}} // Wrong </br>

this.state.comment = 'Hello';

{{% /alert %}}

Instead, use setState():

{{% alert theme="info" %}} // Correct </br>

this.setState({comment: 'Hello'});

{{% /alert %}}

### State Updates May Be Asynchronous

React may batch multiple setState() calls into a single update for performance.</br>

Because this.props and this.state may be updated asynchronously, you should not rely on their values for calculating the next state.</br>
Example:

{{% alert theme="danger" %}} // Wrong </br>
this.setState({
  counter: this.state.counter + this.props.increment,
});
{{% /alert %}}
To fix it, use a second form of setState() that accepts a function rather than an object. That function will receive the previous state as the first argument, and the props at the time the update is applied as the second argument:
{{% alert theme="info" %}} // Correct </br>
this.setState((prevState, props) => ({
  counter: prevState.counter + props.increment
}));
{{% /alert %}}

### never manipulate this.state directly.

There are generally two ways for changing data. The first method is to mutate the data by directly changing the values of a variable. The second method is to replace the data with a new copy of the object that also includes desired changes

Example :
Data change with mutation
```
var player = {score: 1, name: 'Jeff'};
player.score = 2;
// Now player is {score: 2, name: 'Jeff'}
```
Data change without mutation
```
var player = {score: 1, name: 'Jeff'};

var newPlayer = Object.assign({}, player, {score: 2});
// Now player is unchanged, but newPlayer is {score: 2, name: 'Jeff'}

// Or if you are using object spread syntax proposal, you can write:
// var newPlayer = {...player, score: 2};
```

The end result is the same but by not mutating (or changing the underlying data) directly we now have an added benefit that can help us increase component and overall application performance.

#### Easier Undo/Redo and Time Travel
Immutability also makes some complex features much easier to implement. Avoiding data mutations lets us keep a reference to older versions of the data, and switch between them if we need to.

#### Tracking Changes
Determining if a mutated object has changed is complex because changes are made directly to the object. This then requires comparing the current object to a previous copy, traversing the entire object tree, and comparing each variable and value. This process can become increasingly complex.

Determining how an immutable object has changed is considerably easier. If the object being referenced is different from before, then the object has changed. That's it.

#### Determining When to Re-render in React
The biggest benefit of immutability in React comes when you build simple pure components. Since immutable data can more easily determine if changes have been made it also helps to determine when a component requires being re-rendered.
```
Note:
state is optional. Since state increases complexity and reduces predictability, a Component without state is preferable. Even though you clearly cant do without state in an interactive app, you should avoid having too many Stateful Components.
```
