---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
 Implements FIFO (First In First Out) collection of objects. 

Three main operations can be performed on Queue and its elements:

- [Enqueue](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.enqueue?view=net-9.0) adds an element to the end of the Queue
- [Dequeue](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.dequeue?view=net-9.0) removes the oldest element from the start of the Queue.
- [Peek](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.peek?view=net-9.0) peek returns the oldest element that is at the start of the Queue.
    

The capacity of a Queue is the number of elements it can hold. As elements are added to a Queue, the capacity is automatically increased as required by reallocating the internal array. The capacity can be decreased by calling [TrimExcess](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.trimexcess?view=net-9.0).

>[!Info]
> Non-generic type is not recommended to use in new code. Use generic types instead.


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```

