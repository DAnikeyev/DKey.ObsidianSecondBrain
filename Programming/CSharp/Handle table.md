---
date_added: 2025-02-18
tags:
  - csharp
---
Up: [Garbage Collector](Garbage%20Collector.md)
___
 Is a data structure to manage references to objects, particularly those that need to be accessed by unmanaged code or have special lifetime requirements.
Types of Handles:
1. **Strong Handles**: These are regular references that prevent the object from being collected by the GC as long as the handle exists.
2. **Weak Handles**: These allow the GC to collect the object if there are no strong references to it. Weak handles are useful for caching scenarios where you don't want the cache to prevent object collection.
3. **Pinned Handles**: These prevent the GC from moving the object in memory, which is necessary when passing object references to unmanaged code that requires a stable memory address.
4. **Async Handles**: Used for asynchronous operations, ensuring that the object remains alive until the operation completes.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
