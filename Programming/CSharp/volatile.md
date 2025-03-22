---
date_added: 2025-02-21
tags:
  - csharp
---
Up: [Modifiers](Modifiers.md)
___
 The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time. Prevents data caching.
 
>[!Info]
> On a multiprocessor system, a volatile read operation does not guarantee to obtain the latest value written to that memory location by any processor. Similarly, a volatile write operation does not guarantee that the value written would be immediately visible to other processors.

volatile keyword can be applied to simple types, like int or [Reference Type](Reference%20Type.md). `long` or `struct` can't be volatile as read-write operations are not atomic. use [[lock]] or [[Interlocked]] instead for them.

## Volatile class

- Volatile.Read(ref val)
- Volatile.Write(ref val, newVal)

Can be used to bypass [JIT](JIT.md) optimizations and ensure thread safety for simple types.


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
