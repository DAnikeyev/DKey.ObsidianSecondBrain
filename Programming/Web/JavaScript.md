---
date_added: 2025-03-13
tags:
  - data
  - web
---
Up: [Format](Format.md) [Web](Web/Web.md)
___
 JavaScript enables accessing the [document object model](Document%20Object%20Model.md) (DOM) from the [[HTML]] [Web Page](Web%20Page.md), which makes it possible to change elements dynamically on the client.
 JavaScript is a lightweight, interpreted programming language that is widely used for [Web](Web/Web.md) development. It enables interactive web pages and dynamic content, and is supported by all modern web browsers.
## Example
```javascript
// JavaScript Example
function greet(name) {
  console.log("Hello, " + name + "!");
}

greet("World");


// TypeScript Example with type annotations
function greet(name: string): void {
  console.log(`Hello, ${name}!`);
}

greet("World");
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
