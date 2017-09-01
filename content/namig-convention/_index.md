+++
title = "Naming Convention"
description = ""
weight = 20
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
