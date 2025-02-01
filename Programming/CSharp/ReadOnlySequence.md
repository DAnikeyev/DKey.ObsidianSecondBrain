---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Memory buffers](Memory%20buffers.md)
___
 ReadOnlySequence is particularly useful when:

- Processing large amounts of data
- Working with network protocols
- Implementing custom binary parsers
- Handling streaming data
- Need to minimize memory allocations and copies

 ```csharp
 public class LargeDataProcessor
{
    public async Task ProcessLargeData(Stream stream)
    {
        const int segmentSize = 4096;
        var firstSegment = new CustomSegment(new byte[segmentSize]);
        var currentSegment = firstSegment;
        
        while (true)
        {
            var memory = currentSegment.Memory;
            int bytesRead = await stream.ReadAsync(memory);
            
            if (bytesRead == 0) break;
            
            if (bytesRead < segmentSize)
            {
                // Last segment
                var sequence = new ReadOnlySequence<byte>(
                    firstSegment, 
                    0, 
                    currentSegment, 
                    bytesRead);
                    
                ProcessSequence(sequence);
                break;
            }
            
            currentSegment = currentSegment.Append(new byte[segmentSize]);
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
