
+++
title = "Redux core concepts"
description = ""
date = "2017-04-24T18:36:24+02:00"
weight = 29
+++


Redux can be broken down into following concepts:</br></br>
<b>store</b>: Manages the states. Mainly there is a dispatch method to dispatch and action. In Redux, you can obtain the state via store.getState() method.</br></br>
<b>action</b>:  is a simple javascript object. An action can be considered as a command to change a state.</br></br>
<b>reducer</b>: decides how to change a state after receiving an action, and thus can be considered the entrance of a state change. A reducer is comprised of functions, and it changes states by taking an action as an argument, in which it then returns a new state.</br></br>
<b>middleware</b>: the middleman between a store.dispatch() and a reducer. Its purpose is to intercept an action that has been</br> dispatched, and modify or even cancel the action before it reaches the reducer.</br></br>

![agence](http://localhost:1313/images/redux.jpg)
As shown above, if we added a new TODO item in a Redux app, we will first create an action with a type ADD_TODO, and then dispatch the action through store.dispatch().

```
// actionCreator

export function addTodo(text) {
  return { type: types.ADD_TODO, text };
}

store.dispatch(addTodo({ text: 'Some Data' });
```

Afterwards, this action will enter the middleware, and finally enter the reducer. Inside the reducer, the state will change accordingly to the action’s type.</br>

```
// reducer

function todos(state, action) {
  switch(action.type) {
    	case 'ADD_TODO':
        	// handle action and return new state here

    }
}

```

n a more complex app, we will need to split up a store’s state into different pieces like we’d do when namespacing. You can do this in Redux by creating different reducers to manage different areas of a state, and then merge them together through combineReducers</br>

![agence](http://localhost:1313/images/redux2.jpg)
