---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
Implemented as a array of buckets with LinkedList collision resolution. It uses EqualityComparer to ensure that two elements are equal. `HashSet<T>` provides efficient set operations such as union, intersection, and difference

## Properties

| [Capacity](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.capacity?view=net-9.0#system-collections-generic-hashset-1-capacity) | Gets the total numbers of elements the internal data structure can hold without resizing.                                                                                                                      |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Comparer](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.comparer?view=net-9.0#system-collections-generic-hashset-1-comparer) | Gets the [IEqualityComparer<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iequalitycomparer-1?view=net-9.0) object that is used to determine equality for the values in the set. |
| [Count](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1.count?view=net-9.0#system-collections-generic-hashset-1-count)          | Gets the number of elements that are contained in a set.                                                                                                                                                       |

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
