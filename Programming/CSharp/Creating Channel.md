---
date_added: 2025-03-22
tags:
  - csharp
---
Up: [Channel T](Channel%20T.md)
___
 **Channel** class provides static methods to create a channel
 
| Method Signature                                                       | Comment                                                                                            |
| ---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `CreateBounded<T>(BoundedChannelOptions, Action<T>)`                   | Creates a bounded channel with the specified options and an action to process items.               |
| `CreateBounded<T>(BoundedChannelOptions)`                              | Creates a bounded channel with the specified options.                                              |
| `CreateBounded<T>(Int32)`                                              | Creates a bounded channel with the specified maximum capacity.                                     |
| `CreateUnbounded<T>()`                                                 | Creates an unbounded channel usable by any number of readers and writers concurrently.             |
| `CreateUnbounded<T>(UnboundedChannelOptions)`                          | Creates an unbounded channel with the specified options.                                           |
| `CreateUnboundedPrioritized<T>()`                                      | Creates an unbounded prioritized channel usable by any number of readers and writers concurrently. |
| `CreateUnboundedPrioritized<T>(UnboundedPrioritizedChannelOptions<T>)` | Creates an unbounded prioritized channel with the specified options.                               |


```cs
using System;
using System.Threading.Channels;

public class MyType
{
    public int Id { get; set; }
    public string Name { get; set; }
}

public class ChannelExample
{
    public static void Main()
    {
        // Create a bounded channel with specific options and an action
        var boundedChannelWithAction = Channel.CreateBounded<MyType>(
            new BoundedChannelOptions(100)
            {
                FullMode = BoundedChannelFullMode.Wait
            },
            item => Console.WriteLine($"Processed: {item.Name}")
        );

        // Create a bounded channel with specific options
        var boundedChannelWithOptions = Channel.CreateBounded<MyType>(
            new BoundedChannelOptions(100)
            {
                FullMode = BoundedChannelFullMode.DropWrite
            }
        );

        // Create a bounded channel with a specified maximum capacity
        var boundedChannelWithCapacity = Channel.CreateBounded<MyType>(100);

        // Create an unbounded channel
        var unboundedChannel = Channel.CreateUnbounded<MyType>();

        // Create an unbounded channel with specific options
        var unboundedChannelWithOptions = Channel.CreateUnbounded<MyType>(
            new UnboundedChannelOptions
            {
                SingleReader = true,
                SingleWriter = true
            }
        );

        // Create an unbounded prioritized channel
        var unboundedPrioritizedChannel = Channel.CreateUnboundedPrioritized<MyType>();

        // Create an unbounded prioritized channel with specific options
        var unboundedPrioritizedChannelWithOptions = Channel.CreateUnboundedPrioritized<MyType>(
            new UnboundedPrioritizedChannelOptions<MyType>
            {
                Comparer = Comparer<MyType>.Create((x, y) => x.Id.CompareTo(y.Id))
            }
        );

        // Example usage of channels
        var writer = boundedChannelWithCapacity.Writer;
        var reader = boundedChannelWithCapacity.Reader;

        // Writing to the channel
        writer.TryWrite(new MyType { Id = 1, Name = "Item1" });

        // Reading from the channel
        if (reader.TryRead(out MyType item))
        {
            Console.WriteLine($"Read: {item.Name}");
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
