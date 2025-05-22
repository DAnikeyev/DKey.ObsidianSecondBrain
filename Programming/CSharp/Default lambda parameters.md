---
date_added: 2025-05-19
tags:
  - csharp
---
Up: [Lambda Expressions](Lambda%20Expressions.md)
___
 Just as ordinary methods can define parameters with default values:
 ```csharp
 void Print (string message = "") => Console.WriteLine (message);
 ```
so, too, can lambda expressions:
 ```csharp
 var print = (string message = "") => Console.WriteLine (message);
 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
