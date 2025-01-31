---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Fundamental Interfaces](Fundamental%20Interfaces.md)
___
  Supports a simple asynchronous iteration over a generic collection. 
  ```csharp
 public interface IAsyncEnumerator<out T> : IAsyncDisposable
 ```
This type parameter is covariant. That is, you can use either the type you specified or any type that is more derived, see [Covariance and contravariance in generics](Covariance%20and%20contravariance%20in%20generics.md)

## Properties

| [Current](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iasyncenumerator-1.current?view=net-9.0#system-collections-generic-iasyncenumerator-1-current) | Gets the element in the collection at the current position of the enumerator. |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |

## Methods

|   |   |
|---|---|
|[DisposeAsync()](https://learn.microsoft.com/en-us/dotnet/api/system.iasyncdisposable.disposeasync?view=net-9.0#system-iasyncdisposable-disposeasync)|Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources asynchronously.<br><br>(Inherited from [IAsyncDisposable](https://learn.microsoft.com/en-us/dotnet/api/system.iasyncdisposable?view=net-9.0))|
|[MoveNextAsync()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iasyncenumerator-1.movenextasync?view=net-9.0#system-collections-generic-iasyncenumerator-1-movenextasync)|Advances the enumerator asynchronously to the next element of the collection.|

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
