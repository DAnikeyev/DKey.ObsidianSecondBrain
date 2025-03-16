---
date_added: 2025-03-16
tags:
  - csharp
---
Up: [Cancellation Token](Cancellation%20Token.md)
___
Create a [Cancellation Token](Cancellation%20Token.md) or signals to a [Cancellation Token](Cancellation%20Token.md) that it should be canceled.


```cs
using System;
using System.Threading;
using System.Threading.Tasks;

namespace CancellationDemo
{
    class Program
    {
        static async Task Main(string[] args)
        {
            // Create a CancellationTokenSource which will be used to signal cancellation.
            using CancellationTokenSource cts = new CancellationTokenSource();

            // Start a long-running asynchronous operation, passing the cancellation token.
            Task longRunningTask = LongRunningOperationAsync(cts.Token);

            Console.WriteLine("Press 'c' to cancel the operation within 5 seconds...");

            // Listen for a key press to trigger cancellation.
            if (Console.ReadKey().KeyChar == 'c')
            {
                cts.Cancel();
                Console.WriteLine("\nCancellation requested.");
            }

            try
            {
                // Await the task completion.
                await longRunningTask;
                Console.WriteLine("Task completed successfully.");
            }
            catch (OperationCanceledException)
            {
                Console.WriteLine("Task was cancelled.");
            }
        }

        // This method simulates a long running operation that supports cancellation.
        static async Task LongRunningOperationAsync(CancellationToken token)
        {
            for (int i = 1; i <= 10; i++)
            {
                // Periodically check if cancellation has been requested.
                token.ThrowIfCancellationRequested();

                Console.WriteLine($"Processing iteration {i}...");
                try
                {
                    // Simulate work.
                    await Task.Delay(1000, token);
                }
                catch (TaskCanceledException)
                {
                    Console.WriteLine("Delay cancelled.");
                    token.ThrowIfCancellationRequested();
                }
            }
            Console.WriteLine("Operation completed without cancellation.");
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
