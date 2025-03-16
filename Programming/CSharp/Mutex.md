---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [WaitHandle](WaitHandle.md)
___
A synchronization primitive that can also be used for interprocess synchronization.

Key Points to Remember:

1. Always release the Mutex in a finally block to ensure it's released even if an exception occurs.
    
2. Use Mutex when you need:
    - Cross-process synchronization
    - Named synchronization objects
    - More complex synchronization scenarios
3. Consider using `lock` statement instead of Mutex when:
    
    - You only need synchronization within the same process
    - You want simpler syntax
    - Performance is critical (lock is faster than Mutex)
4. Common Pitfalls to Avoid:
    
    - Not releasing the Mutex (can cause deadlocks)
    - Using Mutex when a simpler lock would suffice
    - Not handling AbandonedMutexException
    - Creating too many Mutex objects (they are system-wide resources)
## Example
```cs
using System;
using System.Threading;

class Program
{
    // Create a named mutex for inter-process synchronization; 
    // if unnamed, it works only within the same process.
    private static Mutex mutex = new Mutex(false, "Global\\MyUniqueMutexName");

    static void Main()
    {
        Console.WriteLine("Waiting to acquire the mutex...");
        
        // WaitOne() blocks until the mutex is acquired.
        mutex.WaitOne();

        try
        {
            Console.WriteLine("Mutex acquired. Entering critical section.");
            // Critical section: Place your thread-safe code here.
            Thread.Sleep(2000);  // Simulate work by sleeping for 2 seconds.
        }
        finally
        {
            Console.WriteLine("Exiting critical section and releasing mutex.");
            mutex.ReleaseMutex();
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
