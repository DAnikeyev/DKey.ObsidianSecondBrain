---
date_added: 2025-03-22
tags:
  - csharp
---
Up: [Channel T](Channel%20T.md)
___

Provides a base class for channels that support reading elements of type `TRead` and writing elements of type `TWrite`. This specialized class in the `System.Threading.Channels` namespace allows you to create channels where the input type differs from the output type, which is useful for transformation pipelines.

>[!Info]
> It's an abstract class that you have to implement

### Example

```cs
using System;
using System.Threading;
using System.Threading.Channels;
using System.Threading.Tasks;

namespace SimpleTypedChannelDemo
{
    class Program
    {
        static async Task Main(string[] args)
        {
            // Create a derived channel that transforms strings to integers
            var channel = new StringToIntChannel(10);
            
            // Start producer and consumer tasks
            var cts = new CancellationTokenSource();
            cts.CancelAfter(TimeSpan.FromSeconds(5)); // Automatically cancel after 5 seconds
            
            // Run both tasks concurrently
            await Task.WhenAll(
                ProduceStringsAsync(channel.Writer, cts.Token),
                ConsumeIntsAsync(channel.Reader, cts.Token)
            );
        }
        
        // A simple Channel<string, int> implementation
        private class StringToIntChannel : Channel<string, int>
        {
            private readonly Channel<string> _inputChannel;
            private readonly Channel<int> _outputChannel;
            
            public StringToIntChannel(int capacity)
            {
                _inputChannel = Channel.CreateBounded<string>(capacity);
                _outputChannel = Channel.CreateBounded<int>(capacity);
                
                // Start the background transformation process
                _ = ProcessItemsAsync();
            }
            
            private async Task ProcessItemsAsync()
            {
                try
                {
                    await foreach (var item in _inputChannel.Reader.ReadAllAsync())
                    {
                        if (int.TryParse(item, out int result))
                        {
                            await _outputChannel.Writer.WriteAsync(result);
                        }
                    }
                }
                finally
                {
                    _outputChannel.Writer.Complete();
                }
            }
            
            public override ChannelReader<int> Reader => _outputChannel.Reader;
            public override ChannelWriter<string> Writer => _inputChannel.Writer;
        }
        
        // Produces string values
        private static async Task ProduceStringsAsync(ChannelWriter<string> writer, CancellationToken cancellationToken)
        {
            try
            {
                for (int i = 1; i <= 10; i++)
                {
                    string value = i.ToString();
                    await writer.WriteAsync(value, cancellationToken);
                    Console.WriteLine($"Produced: {value}");
                    await Task.Delay(300, cancellationToken);
                }
            }
            catch (OperationCanceledException)
            {
                Console.WriteLine("Producer canceled");
            }
            finally
            {
                writer.Complete();
                Console.WriteLine("Producer completed");
            }
        }
        
        // Consumes integer values
        private static async Task ConsumeIntsAsync(ChannelReader<int> reader, CancellationToken cancellationToken)
        {
            try
            {
                await foreach (var item in reader.ReadAllAsync(cancellationToken))
                {
                    Console.WriteLine($"Consumed: {item} (as integer)");
                    await Task.Delay(500, cancellationToken);
                }
            }
            catch (OperationCanceledException)
            {
                Console.WriteLine("Consumer canceled");
            }
            finally
            {
                Console.WriteLine("Consumer completed");
            }
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
