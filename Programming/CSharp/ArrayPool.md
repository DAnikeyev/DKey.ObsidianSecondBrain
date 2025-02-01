---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Memory buffers](Memory%20buffers.md)
___

For situations where arrays are created and destroyed frequently, resulting in significant memory pressure on the garbage collector

## Constructors

|   |   |
|---|---|
|[ArrayPool<T>()](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1.-ctor?view=net-9.0#system-buffers-arraypool-1-ctor)|Initializes a new instance of the [ArrayPool<T>](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1?view=net-9.0) class.|

## Properties

|   |   |
|---|---|
|[Shared](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1.shared?view=net-9.0#system-buffers-arraypool-1-shared)|Gets a shared [ArrayPool<T>](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1?view=net-9.0) instance.|

## Methods

|   |   |
|---|---|
|[Create()](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1.create?view=net-9.0#system-buffers-arraypool-1-create)|Creates a new instance of the [ArrayPool<T>](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1?view=net-9.0) class.|
|[Create(Int32, Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1.create?view=net-9.0#system-buffers-arraypool-1-create(system-int32-system-int32))|Creates a new instance of the [ArrayPool<T>](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1?view=net-9.0) class using the specified configuration.|
|[Equals(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.object.equals?view=net-9.0#system-object-equals(system-object))|Determines whether the specified object is equal to the current object.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[GetHashCode()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gethashcode?view=net-9.0#system-object-gethashcode)|Serves as the default hash function.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[GetType()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gettype?view=net-9.0#system-object-gettype)|Gets the [Type](https://learn.microsoft.com/en-us/dotnet/api/system.type?view=net-9.0) of the current instance.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[MemberwiseClone()](https://learn.microsoft.com/en-us/dotnet/api/system.object.memberwiseclone?view=net-9.0#system-object-memberwiseclone)|Creates a shallow copy of the current [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0).<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[Rent(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1.rent?view=net-9.0#system-buffers-arraypool-1-rent(system-int32))|Retrieves a buffer that is at least the requested length.|
|[Return(T[], Boolean)](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1.return?view=net-9.0#system-buffers-arraypool-1-return(-0()-system-boolean))|Returns an array to the pool that was previously obtained using the [Rent(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1.rent?view=net-9.0#system-buffers-arraypool-1-rent(system-int32)) method on the same [ArrayPool<T>](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1?view=net-9.0) instance.|
|[ToString()](https://learn.microsoft.com/en-us/dotnet/api/system.object.tostring?view=net-9.0#system-object-tostring)|Returns a string that represents the current object.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|

[](https://learn.microsoft.com/en-us/dotnet/api/system.buffers.arraypool-1?view=net-9.0#applies-to)
 
 ```cs
 using System.Buffers;

// 1. Basic Rent and Return
byte[] buffer = ArrayPool<byte>.Shared.Rent(1024); // Rent a buffer of at least 1024 bytes
try
{
    // Use the buffer here
    // Note: The actual buffer size might be larger than requested
}
finally
{
    // Always return the buffer when done
    ArrayPool<byte>.Shared.Return(buffer);
}
```

## Example

### File operations:
 ```csharp
 public void ProcessLargeFile(string filePath)
{
    // Rent buffer from pool
    byte[] buffer = ArrayPool<byte>.Shared.Rent(8192);
    try
    {
        using (FileStream fs = File.OpenRead(filePath))
        {
            int bytesRead;
            while ((bytesRead = fs.Read(buffer, 0, buffer.Length)) > 0)
            {
                // Process the data in buffer
                ProcessData(buffer, bytesRead);
            }
        }
    }
    finally
    {
        // Always return the buffer to the pool
        ArrayPool<byte>.Shared.Return(buffer);
    }
}
 ```
### Spans
 ```csharp
 public void ProcessDataWithSpan(int size)
{
    byte[] rentedArray = ArrayPool<byte>.Shared.Rent(size);
    try
    {
        // Create a span over the rented array
        Span<byte> buffer = rentedArray;
        
        // Use only the requested size, not the full rented array
        Span<byte> workingBuffer = buffer.Slice(0, size);
        
        // Work with the span
        workingBuffer.Fill(0); // Example operation
    }
    finally
    {
        // Optional: clear the array before returning (true parameter)
        ArrayPool<byte>.Shared.Return(rentedArray, clearArray: true);
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
