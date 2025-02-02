---
date_added: 2025-01-28
tags:
  - csharp
---
Up: [Fundamental Interfaces](Fundamental%20Interfaces.md)
___
`DisposeAsync` allows consumer to perform resource-intensive dispose operations without blocking the main thread. 

You might implement `IAsyncDisposable` in the following situations:

- When developing an asynchronous enumerator that owns unmanaged resources.
- When your class owns unmanaged resources and releasing them requires a resource-intensive I/O operation, such as flushing the contents of an intermediate buffer into a file or sending a packet over a network to close a connection.
## Methods
- DisposeAsync() - It is used to release all the resources used by the object. It returns a [[ValueTask]]

```cs
using System;
using System.Threading.Tasks;

public class AsyncResource : IAsyncDisposable
{
    // Async cleanup logic goes here
    public ValueTask DisposeAsync()
    {
        Console.WriteLine("Disposing asynchronously...");
        // For demonstration, returning completed ValueTask
        return new ValueTask(Task.CompletedTask);
    }
}

public class Demo
{
    public static async Task Main()
    {
        await using (var resource = new AsyncResource())
        {
            Console.WriteLine("Using resource...");
        }
        // resource.DisposeAsync() is automatically called
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
