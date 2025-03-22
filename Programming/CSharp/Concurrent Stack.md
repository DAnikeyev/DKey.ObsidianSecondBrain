---
date_added: 2025-01-27
tags:
  - csharp
---
Up: [Concurrent collection](Concurrent%20collection.md)
___
ConcurrentQueue\<T> and ConcurrentStack\<T> are completely lock-free in this way. They will never take a lock, but they may end up spinning and retrying an operation when faced with contention (when the CAS operations fail). They use [Compare-and-swap loop](Compare-and-swap%20loop.md) and [Interlocked](Interlocked.md) to update the collection.

```cs
using System;
using System.Collections.Concurrent;

public class Program
{
    public static void Main(string[] args)
    {
        // Create a concurrent stack of integers.
        ConcurrentStack<int> stack = new ConcurrentStack<int>();

        // The Push method adds items to the top of the stack.
        stack.Push(10);
        stack.Push(20);
        stack.Push(30);

        Console.WriteLine("Items after pushing 10, 20, 30:");
        foreach (int item in stack)
        {
            Console.WriteLine(item);
        }

        // The TryPeek method returns the object at the top of the stack without removing it.
        if (stack.TryPeek(out int top))
        {
            Console.WriteLine($"\nPeeked item: {top}");
        }

        // The TryPop method removes and returns the object at the top of the stack.
        if (stack.TryPop(out int popped))
        {
            Console.WriteLine($"\nPopped item: {popped}");
        }

        Console.WriteLine("\nItems after popping:");
        foreach (int item in stack)
        {
            Console.WriteLine(item);
        }

        // ConcurrentStack does not have a Clear method.
        // To remove all items, you can repeatedly call TryPop.
        Console.WriteLine("\nPopping all remaining items:");
        while (stack.TryPop(out int next))
        {
            Console.WriteLine($"Popped: {next}");
        }

        Console.WriteLine("\nThe stack is now empty.");
    }
}
```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
