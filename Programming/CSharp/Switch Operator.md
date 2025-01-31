---
date_added: 2025-01-22
tags:
  - csharp
---
Up: [CSharp Operator](CSharp%20Operator.md)
___
You use the `switch` expression to evaluate a single expression from a list of candidate expressions based on a pattern match with an input expression. Can also be used in a [Pattern expressions](Pattern%20expressions).

Do not confuse with [switch](switch.md) statement

 ```cs
public static Orientation ToOrientation(Direction direction) => direction switch
    {
        Direction.Up    => Orientation.North,
        Direction.Right => Orientation.East,
        Direction.Down  => Orientation.South,
        Direction.Left  => Orientation.West,
        _ => throw new ArgumentOutOfRangeException(nameof(direction), $"Not expected direction value: {direction}"),
    };
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
