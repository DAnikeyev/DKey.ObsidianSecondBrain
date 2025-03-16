---
date_added: 2025-03-16
tags:
  - csharp
---
Up: [Asynchronous programming](Asynchronous%20programming.md)
___
 A deadlock in C# is a situation where two or more threads are blocked forever, each waiting for the other to release a resource they need to continue executing. In a typical scenario, thread A might hold a lock on resource X and need a lock on resource Y, while thread B holds a lock on resource Y and needs a lock on resource X. Since neither thread can proceed until the other releases its lock, they stuck waiting indefinitely.
 
```cs
using System;  
using System.Threading;  
using System.Threading.Tasks;  
  
public class DeadlockTaskSimple  
{  
    // Shared synchronization object.  
    static readonly object syncLock = new object();  
    // Event that allows a thread to wait for a signal.  
    static ManualResetEvent resetEvent = new ManualResetEvent(false);  
  
    public static void Run()  
    {        // A task that attempts to acquire the lock in order to signal the event.  
        Task task = Task.Run(() =>  
        {  
            Console.WriteLine("Task started and attempting to acquire the lock.");  
            lock (syncLock)  
            {                Console.WriteLine("Task acquired the lock and sets the event.");  
                resetEvent.Set(); // Signal the main thread.  
                // Simulate some work.                Thread.Sleep(500);  
            }        });  
        // The main thread acquires the lock and then calls wait on the event.  
        lock (syncLock)  
        {            Console.WriteLine("Main thread acquired the lock.");  
            // Here the main thread holds the lock and waits for the event.  
            // However, the task cannot set the event because it needs to acquire the same lock.            Console.WriteLine("Main thread is waiting for the event.");  
            resetEvent.WaitOne();  
            Console.WriteLine("Main thread resumed after receiving the signal.");  
        }  
        // Wait for the task to complete.  
        task.Wait();  
        Console.WriteLine("Program has finished execution.");  
	    }}
```

## **Scenario : Nested** `ConfigureAwait(true)` **Calls**

Consider the following code snippet:
```cs
public async Task DoWorkAsync()  
{  
    // Some asynchronous operation  
    await Task.Delay(1000).ConfigureAwait(true);  
  
    // More asynchronous work that uses ConfigureAwait(true)  
    await AnotherAsyncMethod().ConfigureAwait(true);  
}

```

If `AnotherAsyncMethod` also uses `ConfigureAwait(true)`, it will attempt to resume on the same synchronization context captured by `DoWorkAsync`. However, since `DoWorkAsync` is still waiting for `AnotherAsyncMethod` to complete, and `AnotherAsyncMethod` is waiting for `DoWorkAsync` to release the synchronization context, a deadlock occurs.

## **Scenario : Mixing** `async` **and** `Wait()`

Another common deadlock scenario is mixing `async/await` with the synchronous `Wait()` method:
```cs
public async Task DoWorkAsync()  
{  
    // Some asynchronous operation  
    await Task.Delay(1000).ConfigureAwait(true);  
  
    // Synchronous call using Wait() or Result property  
    AnotherAsyncMethod().Wait();  
}

```

In this case, `DoWorkAsync` captures the synchronization context with `ConfigureAwait(true)`. However, the subsequent synchronous call to `AnotherAsyncMethod().Wait()` blocks the current thread, preventing the continuation from resuming on the captured synchronization context, leading to a deadlock.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
