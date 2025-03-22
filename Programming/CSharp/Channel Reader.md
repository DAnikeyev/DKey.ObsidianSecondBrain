---
date_added: 2025-03-22
tags:
  - csharp
---
Up: [Channel T](Channel%20T.md)
___
The `ChannelReader<T>` class is typically used in asynchronous programming scenarios to consume data that is produced by a [Channel Writer](Channel%20Writer.md). It provides methods to read data from a channel in a non-blocking manner.

## Usage
```cs

// Reading an item with TryRead
if (reader.TryRead(out var item))
{
    Console.WriteLine($"Read: {item}");
}

// Reading asynchronously
await foreach (var item in reader.ReadAllAsync())
{
    Console.WriteLine($"Async read: {item}");
}

// Reading with explicit handling of completion
try
{
    while (await reader.WaitToReadAsync())
    {
        while (reader.TryRead(out var item))
        {
            Console.WriteLine($"Read: {item}");
        }
    }
}
catch (Exception ex)
{
    Console.WriteLine($"Channel error: {ex.Message}");
}

// Waiting for completion
await reader.Completion;
```

## Constructors

|   |   |
|---|---|
|[ChannelReader<T>()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1.-ctor?view=net-9.0#system-threading-channels-channelreader-1-ctor)|Initializes an instance of the [ChannelReader<T>](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1?view=net-9.0) class.|

## Properties

|   |   |
|---|---|
|[CanCount](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1.cancount?view=net-9.0#system-threading-channels-channelreader-1-cancount)|Gets a value that indicates whether [Count](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1.count?view=net-9.0#system-threading-channels-channelreader-1-count) is available for use on this [ChannelReader<T>](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1?view=net-9.0) instance.|
|[CanPeek](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1.canpeek?view=net-9.0#system-threading-channels-channelreader-1-canpeek)|Gets a value that indicates whether [TryPeek(T)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1.trypeek?view=net-9.0#system-threading-channels-channelreader-1-trypeek\(-0@\)) is available for use on this [ChannelReader<T>](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1?view=net-9.0) instance.|
|[Completion](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1.completion?view=net-9.0#system-threading-channels-channelreader-1-completion)|Gets a [Task](https://learn.microsoft.com/en-us/dotnet/api/system.threading.tasks.task?view=net-9.0) that completes when no more data will ever be available to be read from this channel.|
|[Count](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1.count?view=net-9.0#system-threading-channels-channelreader-1-count)|Gets the current number of items available from this channel reader.|

## Methods

|   |   |
|---|---|
|[Equals(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.object.equals?view=net-9.0#system-object-equals\(system-object\))|Determines whether the specified object is equal to the current object.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[GetHashCode()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gethashcode?view=net-9.0#system-object-gethashcode)|Serves as the default hash function.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[GetType()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gettype?view=net-9.0#system-object-gettype)|Gets the [Type](https://learn.microsoft.com/en-us/dotnet/api/system.type?view=net-9.0) of the current instance.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[MemberwiseClone()](https://learn.microsoft.com/en-us/dotnet/api/system.object.memberwiseclone?view=net-9.0#system-object-memberwiseclone)|Creates a shallow copy of the current [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0).<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[ReadAllAsync(CancellationToken)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1.readallasync?view=net-9.0#system-threading-channels-channelreader-1-readallasync\(system-threading-cancellationtoken\))|Creates an [IAsyncEnumerable<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iasyncenumerable-1?view=net-9.0) that enables reading all of the data from the channel.|
|[ReadAsync(CancellationToken)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1.readasync?view=net-9.0#system-threading-channels-channelreader-1-readasync\(system-threading-cancellationtoken\))|Asynchronously reads an item from the channel.|
|[ToString()](https://learn.microsoft.com/en-us/dotnet/api/system.object.tostring?view=net-9.0#system-object-tostring)|Returns a string that represents the current object.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[TryPeek(T)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1.trypeek?view=net-9.0#system-threading-channels-channelreader-1-trypeek\(-0@\))|Attempts to peek at an item from the channel.|
|[TryRead(T)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1.tryread?view=net-9.0#system-threading-channels-channelreader-1-tryread\(-0@\))|Attempts to read an item from the channel.|
|[WaitToReadAsync(CancellationToken)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.channels.channelreader-1.waittoreadasync?view=net-9.0#system-threading-channels-channelreader-1-waittoreadasync\(system-threading-cancellationtoken\))|Returns a [ValueTask<TResult>](https://learn.microsoft.com/en-us/dotnet/api/system.threading.tasks.valuetask-1?view=net-9.0) that will complete when data is available to read.|

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
