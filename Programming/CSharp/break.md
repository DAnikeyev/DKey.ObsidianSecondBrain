---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Jump statement](Jump%20statement.md)
___
 The `break` statement terminates the closest enclosing [Iteration statement](Iteration%20statement.md).
 ```cs
 for (int outer = 0; outer < 5; outer++)
{
    for (int inner = 0; inner < 5; inner++)
    {
        if (inner > outer)
        {
            break;
        }

        Console.Write($"{inner} ");
    }
    Console.WriteLine();
}
// Output:
// 0
// 0 1
// 0 1 2
// 0 1 2 3
// 0 1 2 3 4
```

In [switch](switch.md) loops break transfer control out of switch statement
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
