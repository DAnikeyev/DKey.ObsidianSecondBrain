---
date_added: 2025-03-22
tags:
  - csharp
---
Up: [Channel T](Channel%20T.md)
___
 The `ChannelWriter<T>` class is typically used in asynchronous programming scenarios to produce data that can be consumed by a [Channel Reader](Channel%20Reader.md) . It provides methods to write data to a channel in a non-blocking manner.
```cs
// Writing an item with TryWrite
if (writer.TryWrite(item))
{
    Console.WriteLine($"Written: {item}");
}

// Writing asynchronously
await writer.WriteAsync(item);
Console.WriteLine($"Async written: {item}");

// Completing the writer
writer.Complete();
```

|   |   |
|---|---|
|[ChannelWriter<T>()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelwriter-1.-ctor?view=net-9.0#system-threading-channels-channelwriter-1-ctor)|Initializes an instance of the [ChannelWriter<T>](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelwriter-1?view=net-9.0) class.|

## Methods

|                                                                                                                                                                                                                                                              |                                                                                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Complete(Exception)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelwriter-1.complete?view=net-9.0#system-threading-channels-channelwriter-1-complete\(system-exception\))                                                   | Mark the channel as being complete, meaning no more items will be written to it.                                                                                                                                                   |
| [Equals(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.object.equals?view=net-9.0#system-object-equals\(system-object\))                                                                                                                       | Determines whether the specified object is equal to the current object.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))                                                  |
| [GetHashCode()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gethashcode?view=net-9.0#system-object-gethashcode)                                                                                                                               | Serves as the default hash function.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))                                                                                     |
| [GetType()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gettype?view=net-9.0#system-object-gettype)                                                                                                                                           | Gets the [Type](https://learn.microsoft.com/en-us/dotnet/api/system.type?view=net-9.0) of the current instance.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))          |
| [MemberwiseClone()](https://learn.microsoft.com/en-us/dotnet/api/system.object.memberwiseclone?view=net-9.0#system-object-memberwiseclone)                                                                                                                   | Creates a shallow copy of the current [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0).<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0)) |
| [ToString()](https://learn.microsoft.com/en-us/dotnet/api/system.object.tostring?view=net-9.0#system-object-tostring)                                                                                                                                        | Returns a string that represents the current object.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))                                                                     |
| [TryComplete(Exception)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelwriter-1.trycomplete?view=net-9.0#system-threading-channels-channelwriter-1-trycomplete\(system-exception\))                                          | Attempts to mark the channel as being completed, meaning no more data will be written to it.                                                                                                                                       |
| [TryWrite(T)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelwriter-1.trywrite?view=net-9.0#system-threading-channels-channelwriter-1-trywrite\(-0\))                                                                         | Attempts to write the specified item to the channel.                                                                                                                                                                               |
| [WaitToWriteAsync(CancellationToken)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelwriter-1.waittowriteasync?view=net-9.0#system-threading-channels-channelwriter-1-waittowriteasync\(system-threading-cancellationtoken\)) | Returns a [ValueTask<TResult>](https://learn.microsoft.com/en-us/dotnet/api/system.threading.tasks.valuetask-1?view=net-9.0) that will complete when space is available to write an item.                                          |
| [WriteAsync(T, CancellationToken)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelwriter-1.writeasync?view=net-9.0#system-threading-channels-channelwriter-1-writeasync\(-0-system-threading-cancellationtoken\))             | Asynchronously writes an item to the channel.                                                                                                                                                                                      |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
