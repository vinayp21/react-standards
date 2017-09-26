+++
title = "React with Redux Integration"
description = ""
date = "2017-04-24T18:36:24+02:00"
weight = 31
+++

React and Redux don’t have a direct relationship – Redux controls an app’s state changes, while React renders the view of states.</br>

React’s strength is its virtual DOM to efficiently re-render a view whenever a state has been changed to a new state (which is packaged in props).</br>

We can use React & Redux together by finding the smart component (stateful component) React components, and inside these components we will set Redux’s state as the component’s state. When these states changes, we can trigger the setState method of component to trigger a re-render. This way, React and Redux states will be bound together.</br>

Once we have these smart components, we can break them down into even smaller components by passing Redux states as React props to create the stateless (dumb) components. However, these stateless components are not directly related to Redux, because their behavior is completely determined by props. Whether or not the props came from Redux does not matter to these stateless components. The connect function in React-Redux hooks together the Redux states and Smart Components.</br>

Below is the sample example of a React + Redux application. The entry point of index.js looks like this:</br>

```
// import statements goes here

const store = configureStore();

render(
  <Provider store={store}>
    	<App />
  </Provider>,
    document.getElementById('root')
);
```
In the code above, we can see the app component App is wrapped inside the Provider component, and this Provider component uses a prop to point us to the app’s state: store.</br>

Here’s what our App‘s component containers/App.js should look like:</br>

```
// import statements goes here
import {connect} from 'react-redux';
import {addTodo} from 'actions/TodoActions';

class App extends Component {
  render() {
    	const { todos, addTodo } = this.props;
        return (
        	<div>
            	<Header addTodo={addTodo} />
                <MainSection todos={todos} />
            </div>
        );
    }
}

App.propTypes = {
  todos: PropTypes.array.isRequired,
  actions: PropTypes.object.isRequired,
  addTodo: PropTypes.func
};


const mapStateToProps = (state) => {
  return {
    	todos: state.todos
    };
};

const mapDispatchToProps = {
  return {
    	addTodo
    };
}
export default connect(mapStateToProps, mapDispatchToProps)(App);
```

Here we’ll see that App is actually just a simple React component and seems to have little to do with Redux.M</br>
However, in the end the .js file does not export the App component directly, but exports the returned result of connect. The connect function will integrate Redux into our App component.</br>
At the connect stage, we’ll pass mapStateToProps and mapDispatchToProps into connect.</br>

mapStateToProps filters the results of Redux states (store.getState()) into something that a Smart component needs, and then passes those into a component as a prop.</br>

mapDispatchToProps takes a set of action creators (which simply return action objects) and make them “dispatchable”. It then passes the object to components as a prop.</br>

connect gets the store through the Provider you saw in index.js.</br>
In index.js, we passed the store into our Provider as a prop, and Provider will set the store as its own React context *. This way, all the child components of the Provider can obtain the store through context. Thus, an App that has been connected can also obtain the store through context.</br>
