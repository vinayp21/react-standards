+++
title = "Introducing JSX"
description = ""
weight = 21
+++

{{% alert theme="info"%}}
const element = \<MyCounter count={3 + 5} />{{% /alert %}}

This syntax is neither a string nor HTML.

It is JSX, and it is a syntax extension to JavaScript. This is recommended with React to describe what the UI should look like. JSX may remind you of a template language, but it comes with the full power of JavaScript.

Do not get confused in JSX syntax and .jsx file extension. JSX can be written in a file with extension of both .js/.jsx

In order to compile JSX to JS , we need transpilers such as Babel.

{{% alert theme="info"%}}
We recommend searching for a "Babel" syntax scheme for your editor of choice so that both ES6 and JSX code is properly highlighted.
{{% /alert %}}
