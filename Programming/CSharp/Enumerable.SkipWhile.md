---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
 Bypasses elements in a sequence as long as a specified condition is true and then returns the remaining elements. Selector can also parse index:
 ```cs
IEnumerable<int> query =
    amounts.SkipWhile((amount, index) => amount > index * 1000);
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
