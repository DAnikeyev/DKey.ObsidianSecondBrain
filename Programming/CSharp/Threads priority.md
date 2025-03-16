---
date_added: 2025-03-15
tags:
  - csharp
---
Up: [Windows Thread](Windows%20Thread.md)
___

| Relative Thread Priority | Process Priority Class | Idle | Below Normal | Normal | Above Normal | High | Realtime |
|--------------------------|------------------------|------|--------------|--------|--------------|------|----------|
| Time-Critical            |                        | 15   | 15           | 15     | 15           | 15   | 31       |
| Highest                  |                        | 6    | 8            | 10     | 12           | 15   | 26       |
| Above Normal             |                        | 5    | 7            | 9      | 11           | 14   | 25       |
| Normal                   |                        | 4    | 6            | 8      | 10           | 13   | 24       |
| Below Normal             |                        | 3    | 5            | 7      | 9            | 12   | 23       |
| Lowest                   |                        | 2    | 4            | 6      | 8            | 11   | 22       |
| Idle                     |                        | 1    | 1            | 1      | 1            | 1    | 16       |

```cs
using System;
using System.Threading;

class Program
{
    static void Main()
    {
        // Create a new thread and assign it a method to execute
        Thread myThread = new Thread(new ThreadStart(MyThreadMethod));

        // Set the thread's priority to AboveNormal
        myThread.Priority = ThreadPriority.AboveNormal;

        // Start the thread
        myThread.Start();

        // Wait for the thread to complete
        myThread.Join();

        Console.WriteLine("Main thread completed.");
    }

    static void MyThreadMethod()
    {
        // Simulate some work in the thread
        for (int i = 0; i < 5; i++)
        {
            Console.WriteLine($"Thread is running with priority: {Thread.CurrentThread.Priority}");
            Thread.Sleep(500); // Sleep for 500 milliseconds
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
