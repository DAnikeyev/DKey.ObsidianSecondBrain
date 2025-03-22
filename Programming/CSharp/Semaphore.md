---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [Synchronisation Primitives](Synchronisation%20Primitives.md) [WaitHandle](WaitHandle.md)
___
Semaphore is a synchronization primitive that controls access to a resource pool by maintaining a count. Unlike a mutex (which allows only one thread in a critical section), a semaphore can allow multiple threads to access a limited number of resources concurrently.

The count on a semaphore is decremented each time a thread enters the semaphore, and incremented when a thread releases the semaphore. When the count is zero, subsequent requests block until other threads release the semaphore. When all threads have released the semaphore, the count is at the maximum value specified when the semaphore was created.

### Methods

1. System.Threading.Semaphore  
    • Methods:  
      – WaitOne(): Blocks the current thread until it can enter the semaphore.  
      – Release(): Exits the semaphore, perhaps releasing a waiting thread.  
    • Suitable for interprocess synchronization as it can be named.
    
2. System.Threading.SemaphoreSlim  
    • Methods:  
      – Wait(): A blocking call that waits for access.  
      – WaitAsync(): An asynchronous version of Wait for non-blocking scenarios.  
      – Release(): Releases the semaphore and returns the count after releasing.  
    • Lightweight and preferred when interprocess sharing is not needed.
###  Counter-Based Access Control:

- A semaphore has an internal counter that represents the number of available units/resources.
- When a thread enters the semaphore (using WaitOne or Wait), the count decreases.
- When the thread releases the semaphore (using Release), the count increases.
- If a thread attempts to enter when the count is 0, it blocks until another thread releases the semaphore.

### Types in C#/.NET:

- Semaphore: The classic semaphore, which is a kernel object and can be used for inter-process synchronization if constructed with a name.
- SemaphoreSlim: A lightweight alternative designed for synchronizing threads within a single process. It avoids some of the overhead associated with kernel objects.

### Use Cases:

- Controlling access to a pool of limited resources, such as a connection pool, limited hardware resources, or managing parallel tasks.
- Limiting the number of concurrent operations (for example, capping the number of tasks that run simultaneously).
## Example 1
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


Key Points to Remember:

1. Semaphore vs SemaphoreSlim:
    
    - Use SemaphoreSlim for better performance when synchronization is needed only within a single process
    - Use Semaphore when you need cross-process synchronization
    - SemaphoreSlim supports async/await operations
2. Best Practices:
    
    - Always release semaphores in a finally block
    - Consider using using statements or IDisposable pattern
    - Handle timeouts appropriately
    - Be careful with the initial and maximum count values
3. Common Use Cases:
    - Resource pool management
    - Rate limiting
    - Controlling concurrent access to resources
    - Producer-consumer scenarios
    - Thread synchronization in parallel processing
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
