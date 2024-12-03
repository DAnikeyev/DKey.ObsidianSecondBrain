---
date_added: 2024-12-03
tags:
  - design
  - architecture
---
Up: [Architecture](Architecture.md)
___
# Model-View-ViewModel(MVVM)
## Overview
Like[ Model-View-Controller](MVC.md), MVVM is a design pattern that separates an application into three main components: Model, View, and ViewModel. Separation of concerns is the main principle of MVVM. The Model represents the data and business logic, the View represents the presentation layer, and the ViewModel acts as an intermediary between the Model and View. Unlike MVC, the ViewModel is responsible for handling the user input and updating the Model and View accordingly.
Data binding is a key feature of MVVM, where the ViewModel is bound to the View, and any changes in the ViewModel are automatically reflected in the View. This makes it easier to maintain and test the application. In MVC however, the Controller is responsible for updating the View, which can lead to tight coupling between the Controller and View.
# Usage
MVVM is commonly used in modern web and mobile applications, where the user interface is complex and requires frequent updates. It is also used in desktop applications, where the user interface is data-driven and requires real-time updates.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
