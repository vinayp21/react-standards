+++
title = "Props"
description = ""
weight = 23
+++

## Props are Read-Only

Whether you declare a component as a function or a class, it must never modify its own props

## Props Usage

Always use camelCase for prop names.

{{% alert theme="danger" %}} // bad </br>
\<Foo
  UserName="hello"
  phone_number={12345678}
/>
{{% /alert %}}
{{% alert theme="info" %}} // good </br>
\<Foo
  userName="hello"
  phoneNumber={12345678}
/>
{{% /alert %}}
Omit the value of the prop when it is explicitly true.

{{% alert theme="danger" %}} // bad </br>
\<Foo
  hidden={true}
/>
{{% /alert %}}
{{% alert theme="info" %}} // good </br>
\<Foo
  hidden
/>
{{% /alert %}}
### Always define explicit defaultProps for all non-required props.

propTypes are a form of documentation, and providing defaultProps means the reader of your code doesn’t have to assume as much. In addition, it can mean that your code can omit certain type checks

{{% alert theme="danger" %}} // bad </br>
function SFC({ foo, bar, children }) { </br>
  return \<div>{foo}{bar}{children}\</div>;</br>
}</br>
SFC.propTypes = {</br>
  foo: PropTypes.number.isRequired,</br>
  bar: PropTypes.string,</br>
  children: PropTypes.node,</br>
};
{{% /alert %}}
{{% alert theme="info" %}} // good </br>
function SFC({ foo, bar, children }) {</br>
  return \<div>{foo}{bar}{children}\</div>;</br>
}</br>
SFC.propTypes = {</br>
  foo: PropTypes.number.isRequired,</br>
  bar: PropTypes.string,</br>
  children: PropTypes.node,</br>
};</br>
SFC.defaultProps = {</br>
  bar: '',</br>
  children: null,</br>
};
{{% /alert %}}
### Avoid using an array index as key prop, prefer a unique ID

{{% alert theme="danger" %}} // bad </br>
{todos.map((todo, index) =>
  \<Todo
    {...todo}
    key={index}
  />
)}
{{% /alert %}}

{{% alert theme="info" %}} // GOOD </br>
{todos.map(todo => (
  \<Todo
    {...todo}
    key={todo.id}
  />
))}
{{% /alert %}}

### Changing props and state

| |props|	state|
|:--|:--|:--|
|Can get initial value from parent Component?|	Yes	|Yes|
|Can be changed by parent Component?	|Yes|	No|
|Can set default values inside Component?|	Yes|	Yes|
|Can change inside Component?|	No	|Yes|
|Can set initial value for child Components?|	Yes|	Yes|
|Can change in child Components?|	Yes|	No|
