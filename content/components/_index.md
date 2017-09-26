+++
title = "React Components"
description = ""
weight = 22
+++


## Class vs React.createClass vs stateless components

### Syntax-

| Class | React.createClass | stateless |
|:--|:--|:--|
| const MyComponent = React.createClass({  });| Class MyComponent extends React.Component{  } | Class MyComponent extends React.Component{  }|

### Basic Rules-
<ul>
  <li>Only include one React component per file.</li>
  <li>However, multiple Stateless, or Pure, Components are allowed per file.</li>
  <li>Always use JSX syntax</li>
  <li>Do not use React.createElement unless you're initializing the app from a file that is not JSX</li>
</ul>

Stateless functions should be preferred for simple components that do not have any state (pure functions of their props).
If you have internal state and/or refs, prefer class extends React.Component over React.createClass -

Example-

{{% alert theme="danger" %}} //bad </br>
```jsx
const Listing = React.createClass({
  render() {
      return (
        <div>
          {this.state.hello}
        </div>);
  }
});
```
{{% /alert %}}

{{% alert theme="info"%}}//good</br>
class Listing extends React.Component {</br>

  render() {</br>
    return \<div>{this.state.hello}\</div>;</br>
  }
}{{% /alert %}}

And if you don't have state or refs, prefer normal functions (not arrow functions) over classes:

{{% alert theme="danger" %}} //bad </br>
class Listing extends React.Component {</br>
  render() {</br>
    return \<div>{this.props.hello}\</div>;</br>
  }
}{{% /alert %}}
{{% alert theme="danger" %}} //bad (relying on function name inference is discouraged)</br>
const Listing = ({ hello }) => (</br>
  \<div>{hello}\</div></br>
);{{% /alert %}}

{{% alert theme="info"%}}//good</br>
function Listing({ hello }) {</br>
  return \<div>{hello}\</div>;</br>
}{{% /alert %}}
