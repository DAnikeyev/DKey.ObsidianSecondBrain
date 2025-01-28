---
date_added: 2025-01-29
tags:
  - csharp
---
Up: [Asynchronous programming](Asynchronous%20programming.md)
___

>[!Info]
> If throws an exception, the exception is thrown on the thread that is waiting for the task to complete. Exception is thrown when the task is awaited.

Exception is stored, accessable with Task.Exception property.


# Awaiting tasks efficiently
```csharp
await Task.WhenAll(task1, task2);
```
// or
```cs
var breakfastTasks = new List<Task> { eggsTask, baconTask, toastTask };
while (breakfastTasks.Count > 0)
{
    Task finishedTask = await Task.WhenAny(breakfastTasks);
    if (finishedTask == eggsTask)
    {
        Console.WriteLine("Eggs are ready");
    }
    else if (finishedTask == baconTask)
    {
        Console.WriteLine("Bacon is ready");
    }
    else if (finishedTask == toastTask)
    {
        Console.WriteLine("Toast is ready");
    }
    await finishedTask;
    breakfastTasks.Remove(finishedTask);
}

```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
