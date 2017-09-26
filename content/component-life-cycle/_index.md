+++
title = "Component Life Cycle"
description = ""
weight = 25
+++

## Mounting-

#### Constructor()-

•	Constructor function gets called before the component is mounted

•	Super(props) should be called inside constructor else this.props will be undefined

•	It is the right place to initialize state. If not you don’t bind methods.

#### componentWillMount()-

•	ComponentWillMount gets called before the render function

•	Neither Props nor State should be modified inside this function.

•	Setting state here will not trigger a re-rendering. Hence it is not recommended.

#### render()-

•	This function is always required.

•	It should always return a single child component.

•	You can also return null or false if you don’t want to render anything.

•	Render function should be pure . It should not modify the state of the component.

#### componentDidMount()-
•	Called after render

•	Good place to make network calls.

•	This will be called only once when the component is mounted.

•	Setting state will trigger the re-rendering.



## Updating-

#### componentWillRecieveProps()-

•	invoked before a mounted component receives new props.

•	compare this.props and nextProps to update any state.

•	Not called during the initial render.

#### shouldComponentUpdate()-
•	Gets invoked before rendering when a new props or state is received

•	By Default returns true

•	If returns false then componentWillUpdate, render and componentDidUpdate will not be invoked.

#### componentWillUpdate()-

•	Gets invoked before re-rendering when a new props or state is received.

•	Not called during the initial render

•	If you want to set state use componentWillReceiveProps method instead of componentWillUpdate()

#### componentDidUpdate()-
•	Gets invoked after updating occurs

•	Good place to do network calls as long as you compare the current and previous props

## Unmounting-
#### componentWillUnmount()-
•	Invoked when a component is removed or destroyed.

•	Perform any cleanup in this method
