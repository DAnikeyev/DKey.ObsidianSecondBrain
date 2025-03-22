---
date_added: 2025-03-03
tags:
  - csharp
---
Up: [Asynchronous programming](Asynchronous%20programming.md)
___
 Provides a mechanism that synchronizes access to objects. More functional then [[lock]]. 
## Key methods
- `Enter(Object, Boolean)`: Enters a monitor, blocking the current thread until the current thread is granted the monitor. The method returns a Boolean value that indicates whether the current thread entered the monitor. This helps to release the lock if the thread is interrupted.
- `Exit(Object)`: Exits a monitor. 
-  `Pulse(Object)`: Notifies a thread in the waiting queue of a monitor that it can acquire the monitor. 
- `PulseAll(Object)`: Notifies all waiting threads of a monitor that they can acquire the monitor.
- `Wait(Object)`: Releases the lock on an object and blocks the current thread until it reacquires the lock. The method returns when the calling thread reacquires the lock.

 ```cs
 using System;
using System.Threading;

class Program
{
    // A private object used as the lock.
    private static readonly object _lock = new object();

    static void Main()
    {
        // Start two threads that access the same locked code.
        Thread t1 = new Thread(DoWork);
        Thread t2 = new Thread(DoWork);
        
        t1.Start();
        t2.Start();
        
        t1.Join();
        t2.Join();
    }

    static void DoWork()
    {
        Console.WriteLine("Thread {0} attempting to enter monitor...", Thread.CurrentThread.ManagedThreadId);
        bool lockAcquired = false;
        try
        {
            // Enter the monitor, using a flag to know when the lock has actually been acquired.
            Monitor.Enter(_lock, ref lockAcquired);
            Console.WriteLine("Thread {0} entered monitor.", Thread.CurrentThread.ManagedThreadId);
            
            // Simulate some work.
            Thread.Sleep(500);
        }
        finally
        {
            // Make sure to exit the monitor if the lock was acquired.
            if (lockAcquired)
            {
                Monitor.Exit(_lock);
                Console.WriteLine("Thread {0} exited monitor.", Thread.CurrentThread.ManagedThreadId);
            }
        }
    }
}
```

```cs
using System;
using System.Threading;

class ProducerConsumerExample
{
    // Lock object and shared state
    private static readonly object _lock = new object();
    private static bool _dataReady = false;

    static void Main()
    {
        Thread producer = new Thread(Produce);
        Thread consumer = new Thread(Consume);
        
        consumer.Start();
        producer.Start();
        
        producer.Join();
        consumer.Join();
    }

    static void Produce()
    {
        lock (_lock)
        {
            Console.WriteLine("Producer is producing data...");
            // Simulate production with a delay.
            Thread.Sleep(1000);
            _dataReady = true;
            Console.WriteLine("Producer produced data; signaling consumer.");
            // Signal the waiting consumer.
            Monitor.Pulse(_lock);
        }
    }

    static void Consume()
    {
        lock (_lock)
        {
            // Wait until the data is ready.
            while (!_dataReady)
            {
                Console.WriteLine("Consumer waiting for data...");
                Monitor.Wait(_lock);
            }
            Console.WriteLine("Consumer received data and is processing it...");
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
