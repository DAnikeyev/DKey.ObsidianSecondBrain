---
date_added: 2025-03-22
tags:
  - csharp
---
Up: [High-Performance strategies](High-Performance%20strategies.md)
___
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
