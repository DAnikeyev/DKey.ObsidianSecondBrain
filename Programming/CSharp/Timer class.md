---
date_added: 2025-03-17
tags:
  - csharp
---
Up: [Task Parallel Library](Task%20Parallel%20Library.md)
___
 Allows to schedule a periodical callback on a thread pool thread at a specified time interval.
 `public Timer(TimerCallback callback, Object state,
Timespan dueTime, TimeSpan period);`

Passing Timeout.Infinite(-1), makes the timer to be a single-shot timer.

Timer can be modified or stopped by calling `Change` method.

You can also use Task.Delay to schedule a callback in a similar way.

 ```csharp
 internal static class TimerDemo {
    private static Timer s_timer;

    public static void Main() {
        Console.WriteLine("Checking status every 2 seconds");

        // Create a timer that never fires initially. This ensures
        // that the reference is stored in s_timer before the Status
        // method is activated by a thread from the pool.
        s_timer = new Timer(Status, null, Timeout.Infinite, Timeout.Infinite);

        // Now that s_timer is assigned, we can allow the timer to fire;
        // we know that calling Change in Status won't throw a NullReferenceException.
        s_timer.Change(0, Timeout.Infinite);

        Console.ReadLine(); // Prevent the process from terminating
    }

    // The signature of this method must match the TimerCallback delegate signature
    private static void Status(Object state) {
        // This method runs on a thread from the pool
        Console.WriteLine("In Status at {0}", DateTime.Now);
        Thread.Sleep(1000); // Simulate other work (1 second)

        // Schedule the timer to call the method again in 2 seconds
        s_timer.Change(2000, Timeout.Infinite);

        // When the method returns, the thread goes back to the pool
        // and waits for the next task
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
