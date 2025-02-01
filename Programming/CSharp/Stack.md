---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
 Represents FILO (First-In-Last-Out) collection of objects.
## Main operations:
- `Push(T item)`: Adds an item to the top of the stack.
- `Pop()`: Removes and returns the item at the top of the stack.
- `Peek()`: Returns the item at the top of the stack without removing it.
The capacity of a Stack is the number of elements it can hold. As elements are added to a Stack, the capacity is automatically increased as required by reallocating the internal array. The capacity can be decreased by calling [TrimExcess](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1.trimexcess?view=net-9.0).
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
>[!Info]
> Non-generic type is not recommended to use in new code. Use generic types instead.
