---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [Collection Interface](Collection%20Interface.md)
___
## Properties

|   |   |
|---|---|
|[Count](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection.count?view=net-9.0#system-collections-icollection-count)|Gets the number of elements contained in the [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0).<br><br>(Inherited from [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0))|
|[IsFixedSize](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist.isfixedsize?view=net-9.0#system-collections-ilist-isfixedsize)|Gets a value indicating whether the [IList](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist?view=net-9.0) has a fixed size.|
|[IsReadOnly](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist.isreadonly?view=net-9.0#system-collections-ilist-isreadonly)|Gets a value indicating whether the [IList](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist?view=net-9.0) is read-only.|
|[IsSynchronized](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection.issynchronized?view=net-9.0#system-collections-icollection-issynchronized)|Gets a value indicating whether access to the [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0) is synchronized (thread safe).<br><br>(Inherited from [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0))|
|[Item[Int32]](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist.item?view=net-9.0#system-collections-ilist-item(system-int32))|Gets or sets the element at the specified index.|
|[SyncRoot](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection.syncroot?view=net-9.0#system-collections-icollection-syncroot)|Gets an object that can be used to synchronize access to the [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0).<br><br>(Inherited from [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0))|

## Methods

|   |   |
|---|---|
|[Add(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist.add?view=net-9.0#system-collections-ilist-add(system-object))|Adds an item to the [IList](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist?view=net-9.0).|
|[Clear()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist.clear?view=net-9.0#system-collections-ilist-clear)|Removes all items from the [IList](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist?view=net-9.0).|
|[Contains(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist.contains?view=net-9.0#system-collections-ilist-contains(system-object))|Determines whether the [IList](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist?view=net-9.0) contains a specific value.|
|[CopyTo(Array, Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection.copyto?view=net-9.0#system-collections-icollection-copyto(system-array-system-int32))|Copies the elements of the [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0) to an [Array](https://learn.microsoft.com/en-us/dotnet/api/system.array?view=net-9.0), starting at a particular [Array](https://learn.microsoft.com/en-us/dotnet/api/system.array?view=net-9.0) index.<br><br>(Inherited from [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0))|
|[GetEnumerator()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable.getenumerator?view=net-9.0#system-collections-ienumerable-getenumerator)|Returns an enumerator that iterates through a collection.<br><br>(Inherited from [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0))|
|[IndexOf(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist.indexof?view=net-9.0#system-collections-ilist-indexof(system-object))|Determines the index of a specific item in the [IList](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist?view=net-9.0).|
|[Insert(Int32, Object)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist.insert?view=net-9.0#system-collections-ilist-insert(system-int32-system-object))|Inserts an item to the [IList](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist?view=net-9.0) at the specified index.|
|[Remove(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist.remove?view=net-9.0#system-collections-ilist-remove(system-object))|Removes the first occurrence of a specific object from the [IList](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist?view=net-9.0).|
|[RemoveAt(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist.removeat?view=net-9.0#system-collections-ilist-removeat(system-int32))|Removes the [IList](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ilist?view=net-9.0) item at the specified index.|
## Extension Methods

|   |   |
|---|---|
|[Cast<TResult>(IEnumerable)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.enumerable.cast?view=net-9.0#system-linq-enumerable-cast-1(system-collections-ienumerable))|Casts the elements of an [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0) to the specified type.|
|[OfType<TResult>(IEnumerable)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.enumerable.oftype?view=net-9.0#system-linq-enumerable-oftype-1(system-collections-ienumerable))|Filters the elements of an [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0) based on a specified type.|
|[AsParallel(IEnumerable)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.parallelenumerable.asparallel?view=net-9.0#system-linq-parallelenumerable-asparallel(system-collections-ienumerable))|Enables parallelization of a query.|
|[AsQueryable(IEnumerable)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.queryable.asqueryable?view=net-9.0#system-linq-queryable-asqueryable(system-collections-ienumerable))|Converts an [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0) to an [IQueryable](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable?view=net-9.0).|
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
