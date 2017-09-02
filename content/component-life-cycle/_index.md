+++
title = "Component Life Cycle"
description = ""
weight = 21
+++

## Mounting-

#### Constructor()- 

•	Constructor function gets called before the component is mounted

•	Super(props) should be called inside constructor else this.props will be undefined

•	It is the right place to initialize state. If not you don’t bind methods.

#### componentWillMount()-

•	ComponentWillMount gets called before the render function
•	You can update the state in this life cycle. Setting state will not trigger re-rendering

#### render()-

•	This function is always required. You can also return null if you don’t want to render anything
•	Render function should be pure . It should not modify the state of the component.

#### componentDidMount()-
•	Called after render
•	Good place to make network calls
•	Setting state will trigger the re-rendering



## Updating-

#### componentWillRecieveProps()-

•	invoked before a mounted component receives new props
•	compare this.props and nextProps to update any state

#### shouldComponentUpdate()-
•	Gets invoked before rendering when a new props or state is received
•	By Default returns true
•	If returns false then componentWillUpdate, render and componentDidUpdate will not be invoked.

#### componentWillUpdate()-

•	Gets invoked before rendering when a new props or state is received.
•	Not called during the initial render
•	If you want to set state use componentWillReceiveProps method instead of componentWillUpdate()

#### componentDidUpdate()-
•	Gets invoked after updating occurs
•	Good place to do network calls as long as you compare the current and previous props

## Unmounting-
#### componentWillUnmount()-
•	Invoked when a component is removed or destroyed.
•	Perform any cleanup in this method 
