+++
title = "Unidirectional data flow"
description = ""
weight = 28
+++

 In React data flows down the tree from parent to child. This makes tracking the source and destination easy compared to other architectures where data may be coming from many parts of the application.

Also the application state is contained in specific stores and as a result different components of your app remain loosely coupled.

Mutation of data is done via actions. So, new data always enters into the store through actions. View components subscribe to the stores and automatically re-render themselves using the new data. So, the data flow looks like this :

Action -> Store -> View
