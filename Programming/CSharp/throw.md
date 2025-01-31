---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Exception handling statements](Exception%20handling%20statements.md)
___
 The `throw` statement throws an [[Exception]]:
 ```cs
 if (shapeAmount <= 0)
{
    throw new ArgumentOutOfRangeException(nameof(shapeAmount), "Amount of shapes must be positive.");
}
```


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
