---
date_added: 2025-02-21
tags:
  - csharp
---
Up: [Collection Interface](Collection%20Interface.md)
___
Provides the base interface for the abstraction of sets. Implemented with [SortedSet](SortedSet.md) or [HashSet](HashSet.md)

## Properties

|   |   |
|---|---|
|[Count](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.count?view=net-9.0#system-collections-generic-icollection-1-count)|Gets the number of elements contained in the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-9.0).<br><br>(Inherited from [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-9.0))|
|[IsReadOnly](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.isreadonly?view=net-9.0#system-collections-generic-icollection-1-isreadonly)|Gets a value indicating whether the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-9.0) is read-only.<br><br>(Inherited from [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-9.0))|

[](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iset-1?view=net-9.0#methods)

## Methods

|   |   |
|---|---|
|[Add(T)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iset-1.add?view=net-9.0#system-collections-generic-iset-1-add\(-0\))|Adds an element to the current set and returns a value to indicate if the element was successfully added.|
|[Clear()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.clear?view=net-9.0#system-collections-generic-icollection-1-clear)|Removes all items from the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-9.0).<br><br>(Inherited from [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-9.0))|
|[Contains(T)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.contains?view=net-9.0#system-collections-generic-icollection-1-contains\(-0\))|Determines whether the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-9.0) contains a specific value.<br><br>(Inherited from [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-9.0))|
|[CopyTo(T[], Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.copyto?view=net-9.0#system-collections-generic-icollection-1-copyto\(-0\(\)-system-int32\))|Copies the elements of the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-9.0) to an [Array](https://learn.microsoft.com/en-us/dotnet/api/system.array?view=net-9.0), starting at a particular [Array](https://learn.microsoft.com/en-us/dotnet/api/system.array?view=net-9.0) index.<br><br>(Inherited from [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-9.0))|
|[ExceptWith(IEnumerable<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iset-1.exceptwith?view=net-9.0#system-collections-generic-iset-1-exceptwith\(system-collections-generic-ienumerable\(\(-0\)\)\))|Removes all elements in the specified collection from the current set.|
|[GetEnumerator()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable.getenumerator?view=net-9.0#system-collections-ienumerable-getenumerator)|Returns an enumerator that iterates through a collection.<br><br>(Inherited from [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0))|
|[IntersectWith(IEnumerable<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iset-1.intersectwith?view=net-9.0#system-collections-generic-iset-1-intersectwith\(system-collections-generic-ienumerable\(\(-0\)\)\))|Modifies the current set so that it contains only elements that are also in a specified collection.|
|[IsProperSubsetOf(IEnumerable<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iset-1.ispropersubsetof?view=net-9.0#system-collections-generic-iset-1-ispropersubsetof\(system-collections-generic-ienumerable\(\(-0\)\)\))|Determines whether the current set is a proper (strict) subset of a specified collection.|
|[IsProperSupersetOf(IEnumerable<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iset-1.ispropersupersetof?view=net-9.0#system-collections-generic-iset-1-ispropersupersetof\(system-collections-generic-ienumerable\(\(-0\)\)\))|Determines whether the current set is a proper (strict) superset of a specified collection.|
|[IsSubsetOf(IEnumerable<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iset-1.issubsetof?view=net-9.0#system-collections-generic-iset-1-issubsetof\(system-collections-generic-ienumerable\(\(-0\)\)\))|Determines whether a set is a subset of a specified collection.|
|[IsSupersetOf(IEnumerable<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iset-1.issupersetof?view=net-9.0#system-collections-generic-iset-1-issupersetof\(system-collections-generic-ienumerable\(\(-0\)\)\))|Determines whether the current set is a superset of a specified collection.|
|[Overlaps(IEnumerable<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iset-1.overlaps?view=net-9.0#system-collections-generic-iset-1-overlaps\(system-collections-generic-ienumerable\(\(-0\)\)\))|Determines whether the current set overlaps with the specified collection.|
|[Remove(T)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.remove?view=net-9.0#system-collections-generic-icollection-1-remove\(-0\))|Removes the first occurrence of a specific object from the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-9.0).<br><br>(Inherited from [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-9.0))|
|[SetEquals(IEnumerable<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iset-1.setequals?view=net-9.0#system-collections-generic-iset-1-setequals\(system-collections-generic-ienumerable\(\(-0\)\)\))|Determines whether the current set and the specified collection contain the same elements.|
|[SymmetricExceptWith(IEnumerable<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iset-1.symmetricexceptwith?view=net-9.0#system-collections-generic-iset-1-symmetricexceptwith\(system-collections-generic-ienumerable\(\(-0\)\)\))|Modifies the current set so that it contains only elements that are present either in the current set or in the specified collection, but not both.|
|[UnionWith(IEnumerable<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iset-1.unionwith?view=net-9.0#system-collections-generic-iset-1-unionwith\(system-collections-generic-ienumerable\(\(-0\)\)\))|Modifies the current set so that it contains all elements that are present in the current set, in the specified collection, or in both.|
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
