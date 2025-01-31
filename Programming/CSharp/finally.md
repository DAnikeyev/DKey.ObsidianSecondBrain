---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Exception handling statements](Exception%20handling%20statements.md)
___
 finally block is executed when the try block exits. This ensures that the finally block is executed even if an unexpected exception occurs. But it is not guaranteed to be executed if the process is terminated.

```cs
public async Task HandleRequest(int itemId, CancellationToken ct)
{
    Busy = true;

    try
    {
        await ProcessAsync(itemId, ct);
    }
    finally
    {
        Busy = false;
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
