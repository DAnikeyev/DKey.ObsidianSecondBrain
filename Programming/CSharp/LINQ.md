---
date_added: 2025-02-24
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
 Is an [[SQL]] - like syntax that converts to [Enumerable](Enumerable.md) calls
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
