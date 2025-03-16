---
date_added: 2025-03-17
tags:
  - csharp
---
Up: [Data parallelism](Data%20parallelism.md) [LINQ](LINQ.md)
___

Through parallel execution, PLINQ can achieve significant performance improvements over legacy code for certain kinds of queries, often just by adding the AsParallel query operation to the data source

Calling AsSequential or AsParallel lets you switch between parallel and sequential execution.

ParallelEnumerable class has mostly same method as [Enumerable](Enumerable.md) class, with some extra like 
 - WithCancellation
 - WithDegreeOfParallelism
 - WithExecutionMode
 - WithMergeOptions
 - ForAll

## Example

```cs
using System;
using System.Linq;

public class Program
{
    public static void Main(string[] args)
    {
        // Create a standard sequence of numbers from 1 to 100.
        var numbers = Enumerable.Range(1, 100);

        // Convert the sequence to a ParallelQuery using AsParallel.
        // This enables parallel execution of subsequent query operations.
        ParallelQuery<int> parallelNumbers = numbers.AsParallel();

        // Use a parallel LINQ (PLINQ) query to filter even numbers.
        var evenNumbers = parallelNumbers.Where(n => n % 2 == 0);

        // Alternatively, you can use ParallelEnumerable.Range to create a parallel sequence directly.
        var evenNumbersFromRange = ParallelEnumerable.Range(1, 100)
                                                     .Where(n => n % 2 == 0);

        // Output the even numbers.
        Console.WriteLine("Even numbers (using AsParallel):");
        foreach (var number in evenNumbers)
        {
            Console.Write(number + " ");
        }
        
        Console.WriteLine("\nEven numbers (using ParallelEnumerable.Range):");
        foreach (var number in evenNumbersFromRange)
        {
            Console.Write(number + " ");
        }
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
