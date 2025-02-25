---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
 Returns a specified number of contiguous elements from the start of a sequence.
 ```cs
IEnumerable<int> topThreeGrades =
    grades.OrderByDescending(grade => grade).Take(3);
```

Can also accept a [[Range]].
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
