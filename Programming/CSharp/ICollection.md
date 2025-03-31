---
date_added: 2025-01-28
tags:
  - csharp
---
Up: [Collection Interface](Collection%20Interface.md)
___
## Properties

|   |   |
|---|---|
|[Count](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.count?view=net-8.0#system-collections-generic-icollection-1-count)|Gets the number of elements contained in the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-8.0).|
|[IsReadOnly](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.isreadonly?view=net-8.0#system-collections-generic-icollection-1-isreadonly)|Gets a value indicating whether the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-8.0) is read-only.|

## Methods

|   |   |
|---|---|
|[Add(T)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.add?view=net-8.0#system-collections-generic-icollection-1-add\(-0\))|Adds an item to the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-8.0).|
|[Clear()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.clear?view=net-8.0#system-collections-generic-icollection-1-clear)|Removes all items from the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-8.0).|
|[Contains(T)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.contains?view=net-8.0#system-collections-generic-icollection-1-contains\(-0\))|Determines whether the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-8.0) contains a specific value.|
|[CopyTo(T[], Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.copyto?view=net-8.0#system-collections-generic-icollection-1-copyto\(-0\(\)-system-int32\))|Copies the elements of the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-8.0) to an [Array](https://learn.microsoft.com/en-us/dotnet/api/system.array?view=net-8.0), starting at a particular [Array](https://learn.microsoft.com/en-us/dotnet/api/system.array?view=net-8.0) index.|
|[GetEnumerator()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable.getenumerator?view=net-8.0#system-collections-ienumerable-getenumerator)|Returns an enumerator that iterates through a collection.<br><br>(Inherited from [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-8.0))|
|[Remove(T)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1.remove?view=net-8.0#system-collections-generic-icollection-1-remove\(-0\))|Removes the first occurrence of a specific object from the [ICollection<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.icollection-1?view=net-8.0).|

## Extension Methods

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```

## Properties

|   |   |
|---|---|
|[Count](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection.count?view=net-9.0#system-collections-icollection-count)|Gets the number of elements contained in the [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0).|
|[IsSynchronized](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection.issynchronized?view=net-9.0#system-collections-icollection-issynchronized)|Gets a value indicating whether access to the [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0) is synchronized (thread safe).|
|[SyncRoot](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection.syncroot?view=net-9.0#system-collections-icollection-syncroot)|Gets an object that can be used to synchronize access to the [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0).|


## Methods

|   |   |
|---|---|
|[CopyTo(Array, Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection.copyto?view=net-9.0#system-collections-icollection-copyto(system-array-system-int32))|Copies the elements of the [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0) to an [Array](https://learn.microsoft.com/en-us/dotnet/api/system.array?view=net-9.0), starting at a particular [Array](https://learn.microsoft.com/en-us/dotnet/api/system.array?view=net-9.0) index.|
|[GetEnumerator()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable.getenumerator?view=net-9.0#system-collections-ienumerable-getenumerator)|Returns an enumerator that iterates through a collection.<br><br>(Inherited from [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0))|

## Extension Methods

|                                                                                                                                                                                                          |                                                                                                                                                                                                                           |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Cast<TResult>(IEnumerable)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.enumerable.cast?view=net-9.0#system-linq-enumerable-cast-1(system-collections-ienumerable))                        | Casts the elements of an [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0) to the specified type.                                                                   |
| [OfType<TResult>(IEnumerable)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.enumerable.oftype?view=net-9.0#system-linq-enumerable-oftype-1(system-collections-ienumerable))                  | Filters the elements of an [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0) based on a specified type.                                                             |
| [AsParallel(IEnumerable)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.parallelenumerable.asparallel?view=net-9.0#system-linq-parallelenumerable-asparallel(system-collections-ienumerable)) | Enables parallelization of a query.                                                                                                                                                                                       |
| [AsQueryable(IEnumerable)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.queryable.asqueryable?view=net-9.0#system-linq-queryable-asqueryable(system-collections-ienumerable))                | Converts an [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0) to an [IQueryable](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable?view=net-9.0). |
