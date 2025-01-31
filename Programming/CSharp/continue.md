---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Jump statement](Jump%20statement.md)
___
 The `continue` statement starts a new iteration of the closest enclosing [Iteration statement](Iteration%20statement.md)
 ```cs
 for (int i = 0; i < 5; i++)
{
    Console.Write($"Iteration {i}: ");
    
    if (i < 3)
    {
        Console.WriteLine("skip");
        continue;
    }
    
    Console.WriteLine("done");
}
// Output:
// Iteration 0: skip
// Iteration 1: skip
// Iteration 2: skip
// Iteration 3: done
// Iteration 4: done
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
