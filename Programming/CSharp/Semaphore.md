---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [WaitHandle](WaitHandle.md)
___
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
