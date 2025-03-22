---
date_added: 2025-01-27
tags:
  - csharp
---
Up: [[Concurrent collection]]
___
 Bags are useful for storing objects when ordering doesn't matter, and unlike sets, bags support duplicates.
 ConcurrentBag\<T> employs a multitude of mechanisms to minimize the need for synchronization.  For example, it maintains a local queue for each thread that accesses it, and under some conditions, a thread is able to access its local queue in a lock-free manner with little or no contention

Store object relative to the thread, try to peek objects from current thread collection first, and then steal them from other threads bags.

## Constructors

|   |   |
|---|---|
|[ConcurrentBag<T>()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1.-ctor?view=net-9.0#system-collections-concurrent-concurrentbag-1-ctor)|Initializes a new instance of the [ConcurrentBag<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1?view=net-9.0) class.|
|[ConcurrentBag<T>(IEnumerable<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1.-ctor?view=net-9.0#system-collections-concurrent-concurrentbag-1-ctor(system-collections-generic-ienumerable((-0))))|Initializes a new instance of the [ConcurrentBag<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1?view=net-9.0) class that contains elements copied from the specified collection.|


## Properties

|   |   |
|---|---|
|[Count](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1.count?view=net-9.0#system-collections-concurrent-concurrentbag-1-count)|Gets the number of elements contained in the [ConcurrentBag<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1?view=net-9.0).|
|[IsEmpty](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1.isempty?view=net-9.0#system-collections-concurrent-concurrentbag-1-isempty)|Gets a value that indicates whether the [ConcurrentBag<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1?view=net-9.0) is empty.|

## Methods

|   |   |
|---|---|
|[Add(T)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1.add?view=net-9.0#system-collections-concurrent-concurrentbag-1-add(-0))|Adds an object to the [ConcurrentBag<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1?view=net-9.0).|
|[Clear()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1.clear?view=net-9.0#system-collections-concurrent-concurrentbag-1-clear)|Removes all values from the [ConcurrentBag<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1?view=net-9.0).|
|[CopyTo(T[], Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1.copyto?view=net-9.0#system-collections-concurrent-concurrentbag-1-copyto(-0()-system-int32))|Copies the [ConcurrentBag<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1?view=net-9.0) elements to an existing one-dimensional [Array](https://learn.microsoft.com/en-us/dotnet/api/system.array?view=net-9.0), starting at the specified array index.|
|[Equals(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.object.equals?view=net-9.0#system-object-equals(system-object))|Determines whether the specified object is equal to the current object.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[GetEnumerator()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1.getenumerator?view=net-9.0#system-collections-concurrent-concurrentbag-1-getenumerator)|Returns an enumerator that iterates through the [ConcurrentBag<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1?view=net-9.0).|
|[GetHashCode()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gethashcode?view=net-9.0#system-object-gethashcode)|Serves as the default hash function.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[GetType()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gettype?view=net-9.0#system-object-gettype)|Gets the [Type](https://learn.microsoft.com/en-us/dotnet/api/system.type?view=net-9.0) of the current instance.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[MemberwiseClone()](https://learn.microsoft.com/en-us/dotnet/api/system.object.memberwiseclone?view=net-9.0#system-object-memberwiseclone)|Creates a shallow copy of the current [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0).<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[ToArray()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1.toarray?view=net-9.0#system-collections-concurrent-concurrentbag-1-toarray)|Copies the [ConcurrentBag<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1?view=net-9.0) elements to a new array.|
|[ToString()](https://learn.microsoft.com/en-us/dotnet/api/system.object.tostring?view=net-9.0#system-object-tostring)|Returns a string that represents the current object.<br><br>(Inherited from [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0))|
|[TryPeek(T)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1.trypeek?view=net-9.0#system-collections-concurrent-concurrentbag-1-trypeek(-0@))|Attempts to return an object from the [ConcurrentBag<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1?view=net-9.0) without removing it.|
|[TryTake(T)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1.trytake?view=net-9.0#system-collections-concurrent-concurrentbag-1-trytake(-0@))|Attempts to remove and return an object from the [ConcurrentBag<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.concurrent.concurrentbag-1?view=net-9.0).|

## Explicit Interface Implementations
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
