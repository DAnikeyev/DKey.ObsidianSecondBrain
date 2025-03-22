---
date_added: 2025-03-22
tags:
  - csharp
---
Up: [Synchronisation](Synchronisation.md) [Stream](Stream.md), [Producer-Consumer Pattern](Producer-Consumer%20Pattern.md)
___
 Is an example for [Producer-Consumer Pattern](Producer-Consumer%20Pattern.md)


### Async Read/Write

1. **Preventing Thread Blocking**
    - When a channel is full (bounded channels) or empty, a synchronous operation would block the thread
    - Async operations allow the thread to be released and used for other work
    - For server applications, this prevents thread pool starvation
2. **Handling Backpressure**
    - When a producer is faster than a consumer, the channel fills up
    - `WriteAsync()` can pause the producer without blocking a thread
    - Similarly, `ReadAsync()` can wait for items without consuming resources
3. **Scalability**
    - Async operations dramatically improve the scalability of applications
    - A server can handle thousands of active channels with minimal threads
    - This is particularly important in high-throughput scenarios
## Example

####  Creation
```cs
var channel = Channel.CreateBounded<WorkItem>(new BoundedChannelOptions(10)
{
    FullMode = BoundedChannelFullMode.Wait // Block when the channel is full
});
```

#### Producer
 ```csharp
 private static async Task ProduceWorkItemsAsync(
    ChannelWriter<WorkItem> writer,
    CancellationToken cancellationToken)
{
    // ... 
    await writer.WriteAsync(workItem, cancellationToken);
    // ...
}
 ```

#### Consumer
 ```csharp
 private static async Task ConsumeWorkItemsAsync(
    ChannelReader<WorkItem> reader,
    CancellationToken cancellationToken)
{
    // ...
    await foreach (var workItem in reader.ReadAllAsync(cancellationToken))
    {
        // Process workItem
    }
    // ...
}
 ``` 

#### Completion:
```cs
// When producers are done
channel.Writer.Complete();

// Then wait for consumers to finish processing remaining items
await Task.WhenAll(consumers);
```

### Batch processing
```cs
// In consumer:
while (await reader.WaitToReadAsync(cancellationToken))
{
    var batch = new List<WorkItem>();
    
    // Read up to 10 items
    while (batch.Count < 10 && reader.TryRead(out var item))
    {
        batch.Add(item);
    }
    
    // Process batch
    await ProcessBatchAsync(batch, cancellationToken);
}
```


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
