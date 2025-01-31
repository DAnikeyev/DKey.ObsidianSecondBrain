---
date_added: 2025-01-30
tags:
  - csharp
---
Up: [Delegate](Delegate.md)
___
 ```cs
 using System;

// Define a delegate that matches the signature of the callback method
public delegate void CallbackDelegate(string result);

public class Worker
{
    // Method that performs some work and then calls the callback
    public void DoWork(CallbackDelegate callback)
    {
        // Simulate some work
        Console.WriteLine("Working...");

        // After work is done, call the callback function
        string result = "Work completed successfully!";
        callback(result);
    }
}

public class Program
{
    // Callback method that matches the delegate signature
    public static void WorkCompletedCallback(string result)
    {
        Console.WriteLine("Callback received: " + result);
    }

    public static void Main()
    {
        Worker worker = new Worker();

        // Pass the callback method to the DoWork method
        worker.DoWork(WorkCompletedCallback);

        // Alternatively, you can use a lambda expression as a callback
        worker.DoWork(result => Console.WriteLine("Lambda callback received: " + result));
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
