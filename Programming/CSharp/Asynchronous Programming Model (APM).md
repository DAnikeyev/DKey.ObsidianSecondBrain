---
date_added: 2025-04-02
tags:
  - csharp
---
Up: [Asynchronous programming](Asynchronous%20programming.md)
___

### Positives
 - Template is simple (BeginXXX, EndXXX)
 - Can be converted to task using [TaskFactory](TaskFactory.md).FromAsync
```cs
public Task<TResult> FromAsync(IAsyncResult asyncResult, Func<IAsyncResult, TResult> endMethod);
```

### Negatives
 - Waiting for the operation to complete is still not optimal
 - Hard to weave multiple dependent operations together
 ![](Pasted%20image%2020250402204409.png)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
