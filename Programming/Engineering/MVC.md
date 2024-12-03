---
date_added: 2024-12-03
tags:
  - design
  - architecture
---
Up: [Architecture](Architecture.md)
___
# Model-View-Controller (MVC)
## Overview

Design pattern that separates an application into three main components: Model, View, and Controller. Separation of concerns is the main principle of MVC. The Model represents the data and business logic, the View represents the presentation layer, and the Controller acts as an intermediary between the Model and View.

>[!Info]
> Controller should not contain any complex logic, it should only handle the user input and update the Model and View accordingly.
# Usage
MVC is commonly used in web applications, where the user interface is simple and requires minimal updates. It is also used in desktop applications, where the user interface is static and requires infrequent updates.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
