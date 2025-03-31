---
date_added: 2025-03-17
tags:
  - csharp
---
Up: [Synchronisation Primitives](Synchronisation%20Primitives.md) [EventWaitHandle](EventWaitHandle.md)
___

AutoResetEvent and ManualResetEvent are synchronization primitives provided by .NET that are used to allow threads to communicate with each other by signaling events.

  
• Key Methods:  
  – WaitOne(): Blocks the current thread until the ManualResetEvent is in the signaled state. Overloads allow specifying a timeout period.  
  – Set(): Signals the event, releasing all waiting threads. The ManualResetEvent remains signaled, so any threads that call WaitOne after Set will not block until Reset is called.  
  – Reset(): Manually resets the event to the non-signaled state, causing subsequent calls to WaitOne to block until the event is signaled again.

────────────────────────────── AutoResetEvent

• Automatically resets to an unsignaled state after releasing a single waiting thread.  
• Use it when you expect that only one waiting thread should proceed for each signal.  
• Commonly used to serialize access to a resource where each signal represents one available resource slot.

────────────────────────────── ManualResetEvent

• Remains signaled until it is manually reset by calling the Reset() method.  
• Allows multiple waiting threads to proceed when signaled, until it is reset.  
• Useful when you want to release all waiting threads at once and then later control when to return to the unsignaled state.

```cs
using System;
using System.Threading;

class Program
{
    // AutoResetEvent example (initially unsignaled)
    private static AutoResetEvent autoEvent = new AutoResetEvent(false);
    
    // ManualResetEvent example (initially unsignaled)
    private static ManualResetEvent manualEvent = new ManualResetEvent(false);

    static void Main()
    {
        // Launch threads that wait on the AutoResetEvent
        Console.WriteLine("=== AutoResetEvent Example ===");
        for (int i = 1; i <= 3; i++)
        {
            int threadNumber = i;
            new Thread(() =>
            {
                Console.WriteLine($"Thread {threadNumber} waiting on AutoResetEvent...");
                autoEvent.WaitOne();
                Console.WriteLine($"Thread {threadNumber} resumed after AutoResetEvent signal.");
            }).Start();
        }

        // Wait a moment and then signal the AutoResetEvent three times; each signal releases one waiting thread.
        Thread.Sleep(1000);
        for (int i = 0; i < 3; i++)
        {
            Console.WriteLine("Signaling AutoResetEvent.");
            autoEvent.Set();
            Thread.Sleep(500);
        }

        // Launch threads that wait on the ManualResetEvent
        Console.WriteLine("\n=== ManualResetEvent Example ===");
        for (int i = 1; i <= 3; i++)
        {
            int threadNumber = i;
            new Thread(() =>
            {
                Console.WriteLine($"Thread {threadNumber} waiting on ManualResetEvent...");
                manualEvent.WaitOne();
                Console.WriteLine($"Thread {threadNumber} resumed after ManualResetEvent signal.");
            }).Start();
        }

        // Wait a moment and then signal the ManualResetEvent; all waiting threads will be released.
        Thread.Sleep(1000);
        Console.WriteLine("Signaling ManualResetEvent.");
        manualEvent.Set();

        // Allow some time for threads to finish then reset the ManualResetEvent.
        Thread.Sleep(1500);
        Console.WriteLine("Resetting ManualResetEvent.");
        manualEvent.Reset();
    }
}
```

1. AutoResetEvent Example:  
    • Three threads wait on an AutoResetEvent.  
    • Each call to autoEvent.Set() releases one waiting thread and automatically resets to a non-signaled state, ensuring that only one thread is woken up per signal.
    
2. ManualResetEvent Example:  
    • Three threads wait on a ManualResetEvent.  
    • When manualEvent.Set() is called, it stays signaled, allowing all waiting threads to proceed.  
    • Calling manualEvent.Reset() later returns it to the unsignaled state, meaning subsequent threads will block until it is signaled again.
    
>[!Info]
> If many threads are in the WaitOne state, AutomaticResetEvent ensures only 1 WaitOne will work, ManualResetEvent can trigger many WaitOne until Reset is called.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
