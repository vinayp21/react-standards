+++
title = "React Components"
description = ""
weight = 20
+++


## Class vs React.createClass vs stateless components

Syntax-

| Class | React.createClass | stateless |
|:--|:--|:--|
| const MyComponent = React.createClass({  });| Class MyComponent extends React.Component{  } | Class MyComponent extends React.Component{  }|

If you have internal state and/or refs, prefer class extends React.Component over React.createClass -

Example-

{{% alert theme="danger" %}} //bad </br>
const Listing = React.createClass({</br>

  render() {</br>
    return \<div>{this.state.hello}\</div>;</br>
  }
});{{% /alert %}}

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

