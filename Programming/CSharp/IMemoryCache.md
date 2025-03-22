---
date_added: 2025-03-20
tags: []
---
Up: [Cache practices](Cache%20practices.md)
___
MemoryCache is a simple in-memory cache that is suitable for small amounts of data. It is a key-value store that is thread-safe and can be used to cache data in a web application.

>[!Info]
> MemoryCacheOptions is used to configure the MemoryCache. It has properties like ExpirationScanFrequency, SizeLimit, CompactionPercentage, SetAbsoluteExpiration
, and so on.
## Example
 ```cs
// Adding the service in Startup.cs
services.AddMemoryCache();

// Injecting and using in a service
public class MyService
{
    private readonly IMemoryCache _memoryCache;
    private const string CacheKey = "MyDataKey";
    
    public MyService(IMemoryCache memoryCache)
    {
        _memoryCache = memoryCache;
    }
    
    public Data GetData()
    {
        // Try to get from cache first
        if (_memoryCache.TryGetValue(CacheKey, out Data cachedData))
        {
            return cachedData;
        }
        
        // Cache miss - get data from source
        Data freshData = GetDataFromSource();
        
        // Cache the data with options
        var cacheOptions = new MemoryCacheEntryOptions()
            .SetAbsoluteExpiration(TimeSpan.FromMinutes(10))
            .SetSlidingExpiration(TimeSpan.FromMinutes(2))
            .SetPriority(CacheItemPriority.Normal);
            
        _memoryCache.Set(CacheKey, freshData, cacheOptions);
        
        return freshData;
    }
}
```

## IMemoryCache interface
```cs
namespace Microsoft.Extensions.Caching.Memory
{
    public interface IMemoryCache : IDisposable
    {
        // Try to get the value associated with the specified key
        bool TryGetValue(object key, out object value);
        
        // Create or overwrite an entry in the cache
        ICacheEntry CreateEntry(object key);
        
        // Remove the cache entry for the specified key
        void Remove(object key);
    }
}
```

### CancelationToken
```cs
// Create a token source
var tokenSource = new CancellationTokenSource();
var options = new MemoryCacheEntryOptions();

// Add dependency on the token
options.AddExpirationToken(new CancellationChangeToken(tokenSource.Token));

// Cache the entry
_memoryCache.Set("myKey", myValue, options);

// Later, when you want to invalidate this entry:
tokenSource.Cancel();
```

### Linking
```cs
// Create parent entry
using (var parentEntry = _memoryCache.CreateEntry("parent"))
{
    parentEntry.Value = parentValue;
    
    // Create child entry linked to parent
    using (var childEntry = _memoryCache.CreateEntry("child"))
    {
        childEntry.Value = childValue;
        
        // Link to parent - when parent is removed, this will also be removed
        childEntry.AddEntryLink(parentEntry);
    }
}
```
### - **Consider Multiple Caching Layers**:
    - IMemoryCache is great for a single server
    - Complement with distributed caching (IDistributedCache) for multi-server setups
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
