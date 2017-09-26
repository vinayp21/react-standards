+++
title = "Naming Convention"
description = ""
weight = 27
+++


Component class names should always begin with an upper case character. React expects elements starting with a lower case character to be built-in HTML elements and will throw an error if your component starts with one

## Component Naming-

{{% alert theme="info"%}}//good</br>
 var myComponent = React.createClass({ /* ... */ });{{% /alert %}}

{{% alert theme="danger" %}} //bad </br>
var MyComponent = React.createClass({ /* ... */ });{{% /alert %}}

## Reference Naming-

Use PascalCase for React components and camelCase for their instances

{{% alert theme="danger" %}} //bad </br>
import reservationCard from './ReservationCard';</br>{{% /alert %}}
{{% alert theme="danger" %}}//bad </br>
const ReservationItem = \<ReservationCard />;</br> {{% /alert %}}

{{% alert theme="info"%}}//good</br>
 import ReservationCard from './ReservationCard'; </br>{{% /alert %}}
{{% alert theme="info"%}}//good</br>
const reservationItem = \<ReservationCard />;{{% /alert %}}

## File and Folder Naming-
```
/actions/...
/components/common/Link.js
/components/common/...
/components/forms/TextBox.js
/components/forms/TextBox.res/style.css
/components/forms/TextBox.locale/en-US/...
/components/forms/...
/components/layout/App.js - The top-level React component
/components/layout/App.res/style.css
/components/layout/App.locale/en-US/...
/components/layout/Navigation.js
/components/layout/Navigation.res/style.css
/components/layout/Navigation.res/data.json
/components/layout/Navigation.locale/en-US/...
/components/layout/...
/components/pages/Home.js
/components/pages/Home.css
/components/pages/Account/index.js
/components/pages/Account/index.css
/components/pages/...
/core/...
/constants/...
/stores/...
```

## CSS Class Names

CSS class names should be prefixed with a single letter corresponding to the component's type.

For example:
```
Component: /components/forms/TextBox.js, CSS class name: f-textbox { ... }
Component: /components/layout/Navigation.js, CSS class name: l-nagiation { ... }
```
