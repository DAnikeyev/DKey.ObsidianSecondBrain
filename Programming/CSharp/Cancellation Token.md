---
date_added: 2025-01-30
tags:
  - csharp
---
Up: [Asynchronous programming](Asynchronous%20programming.md)
___
A CancellationToken enables cooperative cancellation between [Thread](Thread.md), [ThreadPool](ThreadPool.md)work items, or [[Task]] objects. You create a cancellation token by instantiating a [Cancellation Token Source](Cancellation%20Token%20Source.md) object, which manages cancellation tokens retrieved from its CancellationTokenSource.Token property. You then pass the cancellation token to any number of threads, tasks, or operations that should receive notice of cancellation. The token cannot be used to initiate cancellation. When the owning object calls CancellationTokenSource.Cancel, the IsCancellationRequested property on every copy of the cancellation token is set to true. The objects that receive the notification can respond in whatever manner is appropriate.

```cs
using System;
using System.Threading;
using System.Threading.Tasks;

namespace CancellationExample
{
    class Program
    {
        static async Task Main(string[] args)
        {
            // Create a CancellationTokenSource.
            CancellationTokenSource cts = new CancellationTokenSource();

            // Pass the token as a parameter to the asynchronous method.
            Task task = DoWorkAsync(cts.Token);

            Console.WriteLine("Press any key to request cancellation...");
            Console.ReadKey();

            // Request cancellation.
            cts.Cancel();

            try
            {
                // Await the task to handle OperationCanceledException.
                await task;
            }
            catch (OperationCanceledException)
            {
                Console.WriteLine("Task was canceled.");
            }
        }

        // The token is passed as a method parameter, not as part of any context.
        static async Task DoWorkAsync(CancellationToken token)
        {
            for (int i = 0; i < 10; i++)
            {
                // Check if cancellation has been requested.
                token.ThrowIfCancellationRequested();

                Console.WriteLine($"Working... iteration {i}");
                await Task.Delay(1000, token);
            }

            Console.WriteLine("Work completed.");
        }
    }
}
```


You can register a callback method with a cancellation token that the runtime calls when the token is canceled. This method can perform cleanup or other tasks that should be performed when the operation is canceled. The callback method is called on the thread that requested the cancellation, and should be designed to be quick and non-blocking.
```cs
cts.Token.Register(() => Console.WriteLine("Cancellation has been triggered."));
```

>[!Info]
> ThrowIfCancellationRequested is a convenience method that throws an OperationCanceledException if the token has been canceled.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
