---
date_added: 2025-03-17
tags:
  - csharp
---
Up: [Synchronisation Primitives](Synchronisation%20Primitives.md)
___
 The Interlocked class is a part of the System.Threading namespace and provides atomic operations for variables shared across multiple threads. It helps implement lock-free synchronization by ensuring that operations like increment, decrement, addition, exchange, and compare-and-swap are performed atomically at the CPU level.

Key Points:

• Atomic Operations:  
– Methods like Increment, Decrement, Add, Exchange, and CompareExchange help to update shared variables atomically.  
– These operations decrease the need for heavier locking constructs, reducing overhead in high-concurrency scenarios.

• Efficiency:  
– Interlocked methods use low-level CPU instructions to ensure atomicity, which can be more efficient than using lock-based approaches.  
– Ideal for scenarios where you perform simple updates or need to guarantee order without the overhead of blocking locks.

• Usage Scenarios:  
– Incrementing counters, managing indices, or updating status flags where race conditions might otherwise occur.  
– Building parts of lock-free algorithms and data structures.


```cs
using System;
using System.Threading;
using System.Threading.Tasks;

class Program
{
    // Shared counter that will be updated atomically
    private static int counter = 0;

    static async Task Main(string[] args)
    {
        // Create multiple tasks that increment the counter concurrently
        Task[] tasks = new Task[10];
        for (int i = 0; i < tasks.Length; i++)
        {
            tasks[i] = Task.Run(() =>
            {
                // Each task performs 1000 increments
                for (int j = 0; j < 1000; j++)
                {
                    // Atomically increment the counter
                    Interlocked.Increment(ref counter);
                }
            });
        }

        // Wait for all tasks to complete
        await Task.WhenAll(tasks);

        // Display the final value of the counter
        Console.WriteLine($"Final counter value: {counter}");
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
