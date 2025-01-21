---
date_added: 2025-01-22
tags:
  - csharp
---
Up: [CSharp Operator](CSharp%20Operator.md)
___

Used to specify [[Namespace]] of a given type or a method.

 ```cs
 using forwinforms = System.Drawing;
using forwpf = System.Windows;

public class Converters
{
    public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
