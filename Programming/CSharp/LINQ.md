---
date_added: 2025-02-24
tags:
  - csharp
sr-due: 2025-03-29
sr-interval: 4
sr-ease: 270
---
Up: [Collection](Collection.md)
___
Language Integrated Query is an [[SQL]] - like syntax that converts to [Enumerable](Enumerable.md) calls
For example
```cs
var data = new List<string>(){"a", "b", "c"};
var result = from item in data
              where item != "a"
              orderby item
              select item;
//Is equivalent to
var result = data.Where(item => item != "a").OrderBy(item => item);
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
