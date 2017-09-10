+++
title = "Event Handling"
description = ""
weight = 20
+++

Handling events in react is similar to handling it in DOM.

#### The syntactic difference between the two is - 
<ul>
  <li>React events are named using camelCase, rather than lowercase.</li>
  <li>With JSX you pass a function as the event handler, rather than a string.</li>
  <li>With React one cannot return false to prevent default behavior in React. You must call preventDefault explicitly.</li>
</ul>



Example of React click event as compared to html -
{{% alert theme="info"%}}
\<button onClick={clickButton}>
React Button Click
\</button>
{{% /alert %}}


Another difference is that you cannot return false to prevent default behavior in React. You must call preventDefault explicitly.

When using React you should generally not need to call addEventListener to add listeners to a DOM element after it is created. Instead, just provide a listener when the element is initially rendered.
When you define a component using an ES6 class, a common pattern is for an event handler to be a method on the class.

For Child Events if we need to update the state of the parent, we can create an event handler in the parent component and pass it as a prop to the child component where we can just call it.

In JavaScript, class methods are not bound by default. If you forget to bind this.handleClick and pass it to onClick, this will be undefined when the function is actually called.

This is not React-specific behavior; it is a part of how functions work in JavaScript. Generally, if you refer to a method without () after it, such as onClick={this.handleClick}, you should bind that method.