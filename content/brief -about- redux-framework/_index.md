+++
title = "Why Redux?"
description = ""
weight = 21
+++

As the javascript single page applications are becoming too complicated to handle, with the current requirements where it needs to manage the state of the application which includes server responses, cached data and locally persisted data which has not yet persisted in server.  

Managing this ever-changing state is very hard. If a model can update another model, then a view can update a model, which updates another model, and this, in turn, might cause another view to update. At some point, you no longer understand what happens in your app as you have lost control over the when, why, and how of its state. When a system is opaque and non-deterministic, it's hard to reproduce bugs or add new features.

Redux attempts to make state mutations predictable by imposing certain restrictions on how and when updates can happen.