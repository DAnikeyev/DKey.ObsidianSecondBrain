---
date_added: 2025-01-29
tags:
  - csharp
---
Up: [Asynchronous programming](Asynchronous%20programming.md)
___
They represent units of asynchronous or concurrent work that can be started, awaited, cancelled, or chained with continuations. Tasks help abstract away most of the complexity involved in multithreaded programming and provide several benefits over manually created threads. Here are some key points:

- They encapsulate asynchronous operations, making it easy to write code that performs non-blocking work.
- Tasks can return results using `Task<TResult>` and enable composition through continuations (e.g., using ContinueWith or [async](async.md) / [await](await.md)).
- They integrate with cancellation tokens, exception handling, and progress reporting, simplifying the implementation of robust asynchronous workflows.
- By default, tasks run on the thread pool; however, you can control task scheduling if needed.
- 

>[!Info]
> If throws an exception, the exception is thrown on the thread that is waiting for the task to complete. Exception is thrown when the task is awaited.

Exception is stored, accessable with Task.Exception property.


>[!Info]
> 
[[ThreadPool]].QueueUserWorkItem(ComputeBoundOp, 5); 
Is the equivalent of 
new Task(ComputeBoundOp, 5).Start();
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
