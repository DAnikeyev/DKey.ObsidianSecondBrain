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
using System.Threading.Tasks;

public class SemaphoreExample
{
    // Create a semaphore that allows up to 3 threads to access the resource simultaneously
    private static SemaphoreSlim semaphore = new SemaphoreSlim(3, 3);
    
    public async Task AccessResourceAsync()
    {
        try
        {
            // Wait until we can get access to the semaphore
            await semaphore.WaitAsync();
            
            Console.WriteLine($"Thread {Thread.CurrentThread.ManagedThreadId} entered critical section");
            
            // Simulate some work
            await Task.Delay(1000);
        }
        finally
        {
            // Always release the semaphore when done
            semaphore.Release();
            Console.WriteLine($"Thread {Thread.CurrentThread.ManagedThreadId} exited critical section");
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
