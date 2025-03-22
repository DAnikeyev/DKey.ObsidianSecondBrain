---
date_added: 2025-03-22
tags:
  - csharp
---
Up: [Bounded Channel Options](Bounded%20Channel%20Options.md) [Unbounded Channel Options](Unbounded%20Channel%20Options.md)
___
### Why It Matters

1. **Performance**:
    - **Synchronous Continuations (`true`)**: If continuations can run synchronously, they may execute immediately on the same thread that completed the operation. This can reduce the overhead of context switching and improve performance, especially in high-throughput scenarios.
    - **Asynchronous Continuations (`false`)**: Continuations are scheduled to run on a different thread, typically from the thread pool. This can introduce some overhead due to context switching but helps avoid potential deadlocks.
2. **Deadlock Avoidance**:
    
    - **Synchronous Continuations**: If a continuation runs synchronously and tries to acquire a lock or resource that the current thread holds, it can lead to a deadlock.
    - **Asynchronous Continuations**: By running on a different thread, the risk of deadlocks is reduced, as the continuation doesn't block the current thread.
3. **Thread Management**:
    
    - **Synchronous Continuations**: Useful when you want to minimize thread usage and maximize throughput by avoiding unnecessary thread pool usage.
    - **Asynchronous Continuations**: Useful when you want to ensure that long-running or blocking operations in continuations do not block the current thread.

 ```cs
 using System;
using System.Threading.Channels;
using System.Threading.Tasks;

public class Example
{
    public static async Task Main()
    {
        var options = new BoundedChannelOptions(1)
        {
            AllowSynchronousContinuations = true // Change to false to see the difference
        };

        var channel = Channel.CreateBounded<int>(options);

        var writer = channel.Writer;
        var reader = channel.Reader;

        // Writer Task
        var writerTask = Task.Run(async () =>
        {
            Console.WriteLine("Starting to write...");
            await writer.WriteAsync(1).ContinueWith(task =>
            {
                Console.WriteLine("Continuation executed after writing.");
            });
            Console.WriteLine("Finished writing.");
            writer.Complete();
        });

        // Reader Task
        var readerTask = Task.Run(async () =>
        {
            await foreach (var item in reader.ReadAllAsync())
            {
                Console.WriteLine($"Read: {item}");
            }
        });

        await Task.WhenAll(writerTask, readerTask);
    }
}
```


## Deadlock potential:

While sync continuation can lead to better performance (no context switching) it might lead to deadlocks
in this scenario if the channel is full writer won't signall
```cs
using System;
using System.Threading;
using System.Threading.Channels;
using System.Threading.Tasks;

public class RealisticDeadlockExample
{
    private static readonly Channel<int> _channel = Channel.CreateBounded<int>(new BoundedChannelOptions(1)
    {
        AllowSynchronousContinuations = true // This can lead to deadlock in this scenario
    });

    private static readonly AutoResetEvent _signal = new AutoResetEvent(false);

    public static async Task Main()
    {
        var producerTask = Task.Run(() => Producer());
        var consumerTask = Task.Run(() => Consumer());

        await Task.WhenAll(producerTask, consumerTask);
    }

    private static void Producer()
    {
        for (int i = 0; i < 5; i++)
        {
            Console.WriteLine($"Producing: {i}");
            _channel.Writer.WriteAsync(i).ContinueWith(task =>
            {
                Console.WriteLine($"Produced: {i}");
                // Signal the consumer that an item is produced
                _signal.Set();
            });
        }
        _channel.Writer.Complete();
    }

    private static async Task Consumer()
    {
        await foreach (var item in _channel.Reader.ReadAllAsync())
        {
            Console.WriteLine($"Consuming: {item}");
            // Wait for the producer to signal that the item is ready
            _signal.WaitOne();
            Console.WriteLine($"Consumed: {item}");
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
