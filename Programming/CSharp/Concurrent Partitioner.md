---
date_added: 2025-01-28
tags:
  - csharp
---
Up: [Concurrent Dictionary](Concurrent%20Dictionary.md)
___
 Is a way to split collection for parallel processing.
 
 ```cs
 using System;
using System.Collections.Concurrent;
using System.Linq;

class Program
{
    static void Main()
    {
        var numbers = Enumerable.Range(1, 100);

        // Create a partitioner for the numbers collection
        var partitioner = Partitioner.Create(numbers);

        // Use PLINQ to process the partitions in parallel
        var results = partitioner.AsParallel().Select(n => ProcessNumber(n)).ToList();

        foreach (var result in results)
        {
            Console.WriteLine(result);
        }
    }

    static int ProcessNumber(int number)
    {
        // Simulate some processing
        return number * number;
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
