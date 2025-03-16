---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Fundamental Interfaces](Fundamental%20Interfaces.md)
___
 Exposes an enumerator that provides asynchronous iteration over values of a specified type.
  ```csharp
 public interface IAsyncEnumerable<out T>
 ```

## Usage example

data source:
 ```csharp
 using System;
using System.Collections.Generic;
using System.Threading.Tasks;

public class DataService
{
    public async IAsyncEnumerable<int> GetDataAsync()
    {
        for (int i = 0; i < 10; i++)
        {
            // Simulate asynchronous data retrieval
            await Task.Delay(500);
            yield return i;
        }
    }
}
 ```
data consumer
```cs
using System;
using System.Threading.Tasks;

public class Program
{
    public static async Task Main(string[] args)
    {
        var dataService = new DataService();

        await foreach (var number in dataService.GetDataAsync())
        {
            Console.WriteLine($"Received number: {number}");
        }
    }
}
```
## Methods

|                                                                                                                                                                                                                                                                          |                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| [GetAsyncEnumerator(CancellationToken)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iasyncenumerable-1.getasyncenumerator?view=net-9.0#system-collections-generic-iasyncenumerable-1-getasyncenumerator(system-threading-cancellationtoken)) | Returns a [IAsyncEnumerator](IAsyncEnumerator.md) that iterates asynchronously through the collection. |

## Extension Methods

|                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ConfigureAwait<T>(IAsyncEnumerable<T>, Boolean)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.tasks.taskasyncenumerableextensions.configureawait?view=net-9.0#system-threading-tasks-taskasyncenumerableextensions-configureawait-1(system-collections-generic-iasyncenumerable((-0))-system-boolean))                                                 | Configures how awaits on the tasks returned from an async iteration will be performed.                                                                                                                                                                                                                                                                        |
| [ToBlockingEnumerable<T>(IAsyncEnumerable<T>, CancellationToken)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.tasks.taskasyncenumerableextensions.toblockingenumerable?view=net-9.0#system-threading-tasks-taskasyncenumerableextensions-toblockingenumerable-1(system-collections-generic-iasyncenumerable((-0))-system-threading-cancellationtoken)) | Converts an [IAsyncEnumerable<T>](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iasyncenumerable-1?view=net-9.0) instance into an [IEnumerable](IEnumerable.md) that enumerates elements in a blocking manner.                                                                                                                      |
| [WithCancellation<T>(IAsyncEnumerable<T>, CancellationToken)](https://learn.microsoft.com/en-us/dotnet/api/system.threading.tasks.taskasyncenumerableextensions.withcancellation?view=net-9.0#system-threading-tasks-taskasyncenumerableextensions-withcancellation-1(system-collections-generic-iasyncenumerable((-0))-system-threading-cancellationtoken))             | Sets the [Cancellation Token](Cancellation%20Token.md) to be passed to [GetAsyncEnumerator(CancellationToken)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.iasyncenumerable-1.getasyncenumerator?view=net-9.0#system-collections-generic-iasyncenumerable-1-getasyncenumerator(system-threading-cancellationtoken)) when iterating. |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
