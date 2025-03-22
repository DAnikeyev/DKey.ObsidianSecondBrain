---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [[Thread]]

Provides a pool of threads that can be used to execute tasks, post work items, process asynchronous I/O, wait on behalf of other threads, and process timers.

The threads in the managed thread pool are background threads. This means that a threadpool will not keep an application running after all foreground threads have exited.

When [[Task]] perform something asynchronously by default the task is scheduled to run on a thread pool thread. 

CLR created 1 thread pool per [Process](CSharp/Process.md) that populates as queries comes in based on availability of an unoccupied thread.

You can set the minimum and maximum number of threads in the thread pool using the ThreadPool.SetMinThreads and ThreadPool.SetMaxThreads methods.


1. **When to Use ThreadPool**:

✅ Good Use Cases:

- Short-lived operations
- CPU-bound tasks
- Parallel processing of small work items
- Background operations that don't require dedicated threads

❌ Avoid Using ThreadPool For:

- Long-running operations
- Operations that require specific thread settings
- Tasks that need to maintain thread affinity
- Operations requiring guaranteed thread availability

```cs
public void ProcessWorkItem()
{
    ThreadPool.QueueUserWorkItem(state =>
    {
        // Process work here
        ProcessData();
    });
}
```

```cs
using System;
using System.Threading;

public class Example 
{
    public static void Main() 
    {
        // Queue the task.
        ThreadPool.QueueUserWorkItem(Thread Proc);
        Console.WriteLine("Main thread does some work, then sleeps.");
        Thread.Sleep(1000);

        Console.WriteLine("Main thread exits.");
    }

    // This thread procedure performs the task.
    static void ThreadProc(Object stateInfo) 
    {
        // No state object was passed to QueueUserWorkItem, so stateInfo is null.
        Console.WriteLine("Hello from the thread pool.");
    }
}
// The example displays output like the following:
//       Main thread does some work, then sleeps.
//       Hello from the thread pool.
//       Main thread exits.
```

>[!Info]
> One difference between `ThreadPool.QueueUserWorkItem` and `Task.Run` I recently realized is the way they handle exceptions.
If an unhanded exception occurs inside `ThreadPool.QueueUserWorkItem` and not handled by global exception handler, it will crash parent thread. On the other hand, unhanded exceptions from `Task.Run` thread will not get propagated until you `await` or `Task.Wait`.
>
> So Use [Task](Processes/Task.md).Run istead

## References
 1. https://learn.microsoft.com/en-us/dotnet/framework/deployment/in-process-side-by-side-execution
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
