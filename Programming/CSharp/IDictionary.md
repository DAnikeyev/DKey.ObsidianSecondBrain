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
|[IsFixedSize](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary.isfixedsize?view=net-9.0#system-collections-idictionary-isfixedsize)|Gets a value indicating whether the [IDictionary](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=net-9.0) object has a fixed size.|
|[IsReadOnly](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary.isreadonly?view=net-9.0#system-collections-idictionary-isreadonly)|Gets a value indicating whether the [IDictionary](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=net-9.0) object is read-only.|
|[IsSynchronized](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection.issynchronized?view=net-9.0#system-collections-icollection-issynchronized)|Gets a value indicating whether access to the [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0) is synchronized (thread safe).<br><br>(Inherited from [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0))|
|[Item[Object]](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary.item?view=net-9.0#system-collections-idictionary-item(system-object))|Gets or sets the element with the specified key.|
|[Keys](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary.keys?view=net-9.0#system-collections-idictionary-keys)|Gets an [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0) object containing the keys of the [IDictionary](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=net-9.0) object.|
|[SyncRoot](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection.syncroot?view=net-9.0#system-collections-icollection-syncroot)|Gets an object that can be used to synchronize access to the [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0).<br><br>(Inherited from [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0))|
|[Values](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary.values?view=net-9.0#system-collections-idictionary-values)|Gets an [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0) object containing the values in the [IDictionary](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=net-9.0) object.|


## Methods

|   |   |
|---|---|
|[Add(Object, Object)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary.add?view=net-9.0#system-collections-idictionary-add(system-object-system-object))|Adds an element with the provided key and value to the [IDictionary](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=net-9.0) object.|
|[Clear()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary.clear?view=net-9.0#system-collections-idictionary-clear)|Removes all elements from the [IDictionary](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=net-9.0) object.|
|[Contains(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary.contains?view=net-9.0#system-collections-idictionary-contains(system-object))|Determines whether the [IDictionary](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=net-9.0) object contains an element with the specified key.|
|[CopyTo(Array, Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection.copyto?view=net-9.0#system-collections-icollection-copyto(system-array-system-int32))|Copies the elements of the [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0) to an [Array](https://learn.microsoft.com/en-us/dotnet/api/system.array?view=net-9.0), starting at a particular [Array](https://learn.microsoft.com/en-us/dotnet/api/system.array?view=net-9.0) index.<br><br>(Inherited from [ICollection](https://learn.microsoft.com/en-us/dotnet/api/system.collections.icollection?view=net-9.0))|
|[GetEnumerator()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary.getenumerator?view=net-9.0#system-collections-idictionary-getenumerator)|Returns an [IDictionaryEnumerator](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionaryenumerator?view=net-9.0) object for the [IDictionary](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=net-9.0) object.|
|[Remove(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary.remove?view=net-9.0#system-collections-idictionary-remove(system-object))|Removes the element with the specified key from the [IDictionary](https://learn.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=net-9.0) object.|


## Extension Methods

|                                                                                                                                                                                                          |                                                                                                                                                                                                                           |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Cast<TResult>(IEnumerable)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.enumerable.cast?view=net-9.0#system-linq-enumerable-cast-1(system-collections-ienumerable))                        | Casts the elements of an [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0) to the specified type.                                                                   |
| [OfType<TResult>(IEnumerable)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.enumerable.oftype?view=net-9.0#system-linq-enumerable-oftype-1(system-collections-ienumerable))                  | Filters the elements of an [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0) based on a specified type.                                                             |
| [AsParallel(IEnumerable)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.parallelenumerable.asparallel?view=net-9.0#system-linq-parallelenumerable-asparallel(system-collections-ienumerable)) | Enables parallelization of a query.                                                                                                                                                                                       |
| [AsQueryable(IEnumerable)](https://learn.microsoft.com/en-us/dotnet/api/system.linq.queryable.asqueryable?view=net-9.0#system-linq-queryable-asqueryable(system-collections-ienumerable))                | Converts an [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0) to an [IQueryable](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable?view=net-9.0). |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
