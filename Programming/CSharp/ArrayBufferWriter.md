---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Memory buffers](Memory%20buffers.md)
___
ArrayBufferWriter is particularly useful when:

- Building up arrays of data incrementally
- Need efficient memory usage for writing data
- Working with binary protocols or formats
- Serializing data
- Need to avoid unnecessary allocations

The main advantages of ArrayBufferWriter are:

- Efficient memory usage
- Minimizes allocations
- Works well with modern Span-based APIs
- Provides direct access to underlying memory
- Automatically handles buffer growth
 
 ```cs
 using System.Buffers;

public class BasicArrayBufferWriterExample
{
    public void BasicUsage()
    {
        // Create a new ArrayBufferWriter with initial capacity
        var writer = new ArrayBufferWriter<byte>(initialCapacity: 1024);

        // Write some data
        byte[] data = new byte[] { 1, 2, 3, 4, 5 };
        writer.Write(data);

        // Get the written data
        ReadOnlySpan<byte> writtenData = writer.WrittenSpan;
        ReadOnlyMemory<byte> writtenMemory = writer.WrittenMemory;
        
        // Get the count of written bytes
        int bytesWritten = writer.WrittenCount;
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
