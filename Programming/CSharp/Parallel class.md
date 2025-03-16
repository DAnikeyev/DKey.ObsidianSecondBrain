---
date_added: 2025-03-17
tags:
  - csharp
---
Up: [Data parallelism](Data%20parallelism.md)
___
 Provides support for parallel loops and regions.
## Methods
    For
    ForAsync
    ForEach
    ForEachAsync
    Invoke
You can use [Partitioner](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.partitioner?view=net-9.0) to optimize many calls of small loops.

Exception during one of the methods will be propogated using [System.AggregateException](System.AggregateException.md)
## Example
 ```cs
 using System;
using System.Collections.Generic;
using System.Threading.Tasks;

class Program
{
    static void Main()
    {
        // Parallel.For Example:
        Console.WriteLine("Parallel.For Example:");
        Parallel.For(0, 5, i =>
        {
            Console.WriteLine($"Iteration {i} processed on Thread {System.Threading.Thread.CurrentThread.ManagedThreadId}");
        });

        // Parallel.ForEach Example:
        Console.WriteLine("\nParallel.ForEach Example:");
        List<string> names = new List<string> { "Alice", "Bob", "Charlie", "Dave" };
        Parallel.ForEach(names, name =>
        {
            Console.WriteLine($"Processing {name} on Thread {System.Threading.Thread.CurrentThread.ManagedThreadId}");
        });

        // Parallel.Invoke Example:
        Console.WriteLine("\nParallel.Invoke Example:");
        Parallel.Invoke(
            () => PerformTask("Task 1"),
            () => PerformTask("Task 2"),
            () => PerformTask("Task 3")
        );

        Console.WriteLine("\nAll tasks complete.");
    }

    static void PerformTask(string taskName)
    {
        // Simulate work by writing the task name and thread id
        Console.WriteLine($"{taskName} is running on Thread {System.Threading.Thread.CurrentThread.ManagedThreadId}");
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
