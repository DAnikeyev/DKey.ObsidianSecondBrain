---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [System.Diagnostics](System.Diagnostics.md)
___
 Is used to obtain information about a thread that is currently running on the system. Doing so allows you, for example, to monitor the thread's performance characteristics. ProcessThreadCollection represents a collection of threads in a process.
 
 >[!Info]
> Implements [IDisposable](IDisposable.md)

## Example
```cs
using System;
using System.Diagnostics;

class Program
{
    static void Main()
    {
        // Get all processes with the name "notepad"
        Process[] processes = Process.GetProcessesByName("notepad");

        foreach (Process process in processes)
        {
            Console.WriteLine($"Process ID: {process.Id}, Process Name: {process.ProcessName}");

            // Get the threads in the process
            ProcessThreadCollection threads = process.Threads;

            foreach (ProcessThread thread in threads)
            {
                Console.WriteLine($"  Thread ID: {thread.Id}");
                Console.WriteLine($"  Thread State: {thread.ThreadState}");
                Console.WriteLine($"  Start Time: {thread.StartTime}");
                Console.WriteLine($"  Priority Level: {thread.CurrentPriority}");
                Console.WriteLine();
            }
        }
    }
}
```

Has info like [[ThreadState]]
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
