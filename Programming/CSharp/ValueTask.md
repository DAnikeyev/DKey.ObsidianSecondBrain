---
date_added: 2025-01-29
tags:
  - csharp
---
Up: [[Task]]
___
 ValueTask is a struct that represents an asynchronous operation that can return a result. It is a value type and is more efficient than Task when the operation completes synchronously. It is used to avoid the overhead of allocating a Task object for each operation that completes synchronously.
 
 Method AsTask() can be used to convert ValueTask to Task.

>[!Info]
> A [ValueTask\<TResult>](https://learn.microsoft.com/en-us/dotnet/api/system.threading.tasks.valuetask-1?view=net-9.0) instance may only be awaited once, and consumers may not read Resultuntil the instance has completed.

## Example

```cs
using System;
using System.Threading.Tasks;

public class DataService
{
    private readonly Cache _cache = new Cache();

    public async ValueTask\<string> GetDataAsync(string key)
    {
        // Check if the data is in the cache
        if (_cache.TryGet(key, out string cachedData))
        {
            // Return synchronously if data is found in the cache
            return cachedData;
        }

        // Otherwise, fetch the data asynchronously
        string data = await FetchDataFromDatabaseAsync(key);
        _cache.Set(key, data);
        return data;
    }

    private async Task\<string> FetchDataFromDatabaseAsync(string key)
    {
        // Simulate asynchronous database access
        await Task.Delay(100); // Simulate delay
        return "Data from database";
    }
}

public class Cache
{
    private readonly System.Collections.Generic.Dictionary<string, string> _store = new();

    public bool TryGet(string key, out string value) => _store.TryGetValue(key, out value);

    public void Set(string key, string value) => _store[key] = value;
}

public class Program
{
    public static async Task Main()
    {
        var dataService = new DataService();

        // First call will fetch from the database
        string data1 = await dataService.GetDataAsync("key1");
        Console.WriteLine(data1); // Outputs: Data from database

        // Second call will retrieve from the cache
        string data2 = await dataService.GetDataAsync("key1");
        Console.WriteLine(data2); // Outputs: Data from database
    }
}
```


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
