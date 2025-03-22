---
date_added: 2025-01-27
tags:
  - csharp
---
Up: [Concurrent collection](Concurrent%20collection.md)
___
 ConcurrentQueue\<T> and ConcurrentStack\<T> are completely lock-free in this way. They will never take a lock, but they may end up spinning and retrying an operation when faced with contention (when the CAS operations fail).  They use [Compare-and-swap loop](Compare-and-swap%20loop.md) and [Interlocked](Interlocked.md) to update the collection.
```cs
using System;
using System.Collections.Concurrent;

public class Program
{
    public static void Main(string[] args)
    {
        // Create a concurrent queue of integers.
        ConcurrentQueue<int> queue = new ConcurrentQueue<int>();

        // The Enqueue method adds items at the end of the queue.
        queue.Enqueue(1);
        queue.Enqueue(2);
        queue.Enqueue(3);

        Console.WriteLine("Items enqueued: 1, 2, 3");

        // The TryPeek method returns the object at the beginning of the queue without removing it.
        if (queue.TryPeek(out int peeked))
        {
            Console.WriteLine($"Peeked item: {peeked}");
        }

        // The TryDequeue method removes and returns the object at the beginning of the queue.
        if (queue.TryDequeue(out int dequeued))
        {
            Console.WriteLine($"Dequeued item: {dequeued}");
        }

        Console.WriteLine("Remaining items in the queue:");
        foreach (int item in queue)
        {
            Console.WriteLine(item);
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
