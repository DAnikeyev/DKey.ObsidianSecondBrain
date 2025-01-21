---
date_added: 2025-01-21
tags:
  - csharp
---
Up: [CSharp Operator](CSharp%20Operator.md)
___
 You can use a _collection expression_ to create common collection values. A _collection expression_ is a terse syntax that, when evaluated, can be assigned to many different collection types.
```cs
Span<string> weekDays = ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"];
foreach (var day in weekDays)
{
    Console.WriteLine(day);
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
