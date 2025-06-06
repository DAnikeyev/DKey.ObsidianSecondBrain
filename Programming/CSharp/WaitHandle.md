---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [Synchronisation Primitives](Synchronisation%20Primitives.md)
___

Encapsulates operating system-specific objects that wait for exclusive access to shared resources. It is abstract class with methods:
 - `WaitOne()`  - Blocks the current thread until the current WaitHandle receives a signal.
 - static `WaitAll()`  - Blocks the current thread until all the WaitHandle objects are in the signaled state.
 - static `WaitAny()`  - Blocks the current thread until one of the WaitHandle objects receives a signal.
 - `Set()`  - Sets the state of the event to signaled, allowing one or more waiting threads to proceed.
You can use it as a static field or pass as a parameter to a method.

 ```cs
public sealed class App
{
    // Define an array with two AutoResetEvent WaitHandles.
    static WaitHandle[] waitHandles = new WaitHandle[]
    {
        new AutoResetEvent(false),
        new AutoResetEvent(false)
    };

    // Define a random number generator for testing.
    static Random r = new Random();

    static void Main()
    {
        // Queue up two tasks on two different threads;
        // wait until all tasks are completed.
        DateTime dt = DateTime.Now;
        Console.WriteLine("Main thread is waiting for BOTH tasks to complete.");
        ThreadPool.QueueUserWorkItem(new WaitCallback(DoTask), waitHandles[0]);
        ThreadPool.QueueUserWorkItem(new WaitCallback(DoTask), waitHandles[1]);
        WaitHandle.WaitAll(waitHandles);
        // The time shown below should match the longest task.
        Console.WriteLine("Both tasks are completed (time waited={0})",
            (DateTime.Now - dt).TotalMilliseconds);

        // Queue up two tasks on two different threads;
        // wait until any task is completed.
        dt = DateTime.Now;
        Console.WriteLine();
        Console.WriteLine("The main thread is waiting for either task to complete.");
        ThreadPool.QueueUserWorkItem(new WaitCallback(DoTask), waitHandles[0]);
        ThreadPool.QueueUserWorkItem(new WaitCallback(DoTask), waitHandles[1]);
        int index = WaitHandle.WaitAny(waitHandles);
        // The time shown below should match the shortest task.
        Console.WriteLine("Task {0} finished first (time waited={1}).",
            index + 1, (DateTime.Now - dt).TotalMilliseconds);
    }

    static void DoTask(Object state)
    {
        AutoResetEvent are = (AutoResetEvent) state;
        int time = 1000 * r.Next(2, 10);
        Console.WriteLine("Performing a task for {0} milliseconds.", time);
        Thread.Sleep(time);
        are.Set();
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
