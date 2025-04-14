---
date_added: 2025-03-17
tags:
  - csharp
---
Up: [Synchronisation Primitives](Synchronisation%20Primitives.md)
___
 SpinLock and SpinWait are synchronization primitives designed to improve performance in scenarios where locks are held for very short durations. They avoid the overhead of kernel-level context switches that occur with traditional OS-managed locks by “spinning” (actively waiting) in a loop until the lock becomes available.
 
##  SpinLock

• A SpinLock is a lightweight, low-level lock that repeatedly checks if it can acquire the lock.  
• It is best suited for short-duration locks, where the cost of a context switch would outweigh the time spent spinning.  
• Since it continuously polls (spins) until the lock is available, it can consume CPU cycles, so it should be used when you’re confident that the lock will be released quickly.  
• SpinLock is not reentrant, which means a thread cannot acquire it multiple times without releasing it first.

## SpinWait

• SpinWait is a utility struct that provides methods to implement efficient spinning.  
• It helps to reduce CPU usage during spinning by incorporating techniques like yielding the processor or performing a brief sleep after spinning for a while.  
• When building custom spin locks or waiting loops, SpinWait helps balance between active spinning and releasing the CPU to prevent excessive consumption.

>[!Info]
> spinOnce do some loops first, then calls [[Thread.Yield]] (which increases [Threads priority](Threads%20priority.md) so it wake up faster) and after that calls `Thread.Sleep` to give up CPU for a while.)


```cs
using System;
using System.Threading;
using System.Threading.Tasks;

public class SpinLockDemo
{
    // Shared value that will be updated
    private static int sharedCounter = 0;
    
    // Create a SpinLock instance. Note that SpinLock is a struct; use caution when copying
    private static SpinLock spinLock = new SpinLock();

    public static async Task Main(string[] args)
    {
        // Launch multiple tasks that increment the shared counter
        Task[] tasks = new Task[5];
        for (int i = 0; i < tasks.Length; i++)
        {
            tasks[i] = Task.Run(() =>
            {
                // Each task will perform 100 increments
                for (int j = 0; j < 100; j++)
                {
                    bool lockTaken = false;
                    try
                    {
                        // Attempt to acquire the spin lock
                        spinLock.Enter(ref lockTaken);

                        // Critical section start
                        sharedCounter++;
                        // Critical section end
                    }
                    finally
                    {
                        // Release the lock if it was taken
                        if (lockTaken)
                        {
                            spinLock.Exit();
                        }
                    }
                    
                    // Optionally, use SpinWait to yield control if needed.
                    // For example, after every 10 increments, yield to avoid excessive CPU usage.
                    if (j % 10 == 0)
                    {
                        var spinner = new SpinWait();
                        spinner.SpinOnce();
                    }
                }
            });
        }
        await Task.WhenAll(tasks);

        Console.WriteLine($"Final shared counter value: {sharedCounter}");
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
