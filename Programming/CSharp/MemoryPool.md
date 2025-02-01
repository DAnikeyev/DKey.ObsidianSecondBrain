---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Memory buffers](Memory%20buffers.md)
___

## Examples
 ```cs
 using System.Buffers;

public void BasicMemoryPoolExample()
{
    // 1. Get a memory pool instance
    MemoryPool<byte> pool = MemoryPool<byte>.Shared;

    // 2. Rent memory from the pool
    using (IMemoryOwner<byte> owner = pool.Rent(1024))
    {
        Memory<byte> memory = owner.Memory;
        // Use the memory here
        
        // 3. Memory is automatically returned when disposed
    } // Automatically returns the memory to the pool
}
```

 ```csharp
 public async Task ProcessNetworkStream(NetworkStream stream, int bufferSize)
{
    using (IMemoryOwner<byte> memoryOwner = MemoryPool<byte>.Shared.Rent(bufferSize))
    {
        Memory<byte> memory = memoryOwner.Memory;
        while (true)
        {
            int bytesRead = await stream.ReadAsync(memory);
            if (bytesRead == 0) break;

            // Process only the bytes that were read
            Memory<byte> actualData = memory.Slice(0, bytesRead);
            await ProcessData(actualData);
        }
    }
}
 ```

Key Differences Table:

| Return Type         | T[] (raw array)                  | IMemoryOwner              |
| ------------------- | -------------------------------- | ------------------------- |
| Memory Access       | Direct array access              | Through Memory/Span       |
| Resource Management | Manual return required           | Automatic via IDisposable |
| Safety              | Less safe (can forget to return) | Safer with using pattern  |
| Performance         | Slightly better (direct access)  | Minimal overhead          |
| Memory Model        | Mutable array                    | Immutable Memory wrapper  |
| Usage Complexity    | More error-prone                 | More structured           |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
