---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [Value Type](Value%20Type.md)
___
 A _nullable value type_ `T?` represents all values of its underlying [Value Type](Value%20Type.md) `T`and an additional [[null]] value
## Lifted operators
```cs
int? a = 10;
int? b = null;
int? c = 10;

a++;        // a is 11
a = a * c;  // a is 110
a = a + b;  // a is null
```

Otherwise nullability has to be checked using HasValue method or [Null-Coalescing Operator](Null-Coalescing%20Operator.md)

Instance of a nullable type is boxes, see [Boxing and Unboxing](Boxing%20and%20Unboxing)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
