---
date_added: 2025-02-27
tags:
  - csharp
---
Up: [Switch Operator](Switch%20Operator.md)
___
 Used to convert between types, either implicitly or explicitly. you can define [Custom Conversion Operators](Custom%20Conversion%20Operators.md)
## Implicit casting
```cs
int a = 123;
long b = a; // Implicit casting from int to long
```

# Explicit casting
Is used when there is potential data loss.
```cs
double x = 123.45;
int y = (int)x; // Explicit casting from double to int
```
>[!Info]
> 
Can throw `InvalidCastException`
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
