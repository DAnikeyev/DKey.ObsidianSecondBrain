---
date_added: 2025-03-22
tags:
  - csharp
---
Up: [High-Performance strategies](High-Performance%20strategies.md)
___
Batching is the practice of grouping multiple operations into a single round-trip or processing step to reduce overhead and improve performance, especially when network latency or I/O operations are involved.
## Examples
```cs
public class BatchingExample
{
    public static IEnumerable<IEnumerable<T>> GetBatches<T>(IEnumerable<T> items, int batchSize)
    {
        List<T> batch = new List<T>(batchSize);

        foreach (var item in items)
        {
            batch.Add(item);
            if (batch.Count == batchSize)
            {
                yield return batch;
                batch = new List<T>(batchSize);
            }
        }

        // Return the final batch if it has leftover items
        if (batch.Any())
        {
            yield return batch;
        }
    }

    public static void ProcessBatches()
    {
        // Example data
        var data = new List<int>();
        for (int i = 1; i <= 100; i++)
        {
            data.Add(i);
        }

        // Split into batches of size 10
        var batches = GetBatches(data, 10);

        // Process each batch
        foreach (var batch in batches)
        {
            // Perform your combined operation here
            // (e.g., a single database or network call for this batch)
            Console.WriteLine($"Processing batch of size {batch.Count()}");
        }
    }
}
```

## In [Channel T](Channel%20T.md)
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

>[!Info]
> You can also batch DataBase operations, network requests, or file I/O to reduce the overhead of individual calls and improve performance.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
