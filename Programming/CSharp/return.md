---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Jump statement](Jump%20statement.md)
___
 The `return` statement terminates execution of the function in which it appears and returns control and the function's result, if any, to the caller.
 ```cs
 Console.WriteLine("First call:");
DisplayIfNecessary(6);

Console.WriteLine("Second call:");
DisplayIfNecessary(5);

void DisplayIfNecessary(int number)
{
    if (number % 2 == 0)
    {
        return;
    }

    Console.WriteLine(number);
}
// Output:
// First call:
// Second call:
// 5
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
