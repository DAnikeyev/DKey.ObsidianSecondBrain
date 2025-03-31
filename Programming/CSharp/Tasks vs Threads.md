---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Task](CSharp/Task.md), [Thread](Thread.md)
___

Tasks:

- ✅ Higher-level abstraction
- ✅ Built-in support for async/await
- ✅ Easy error handling
- ✅ Support for cancellation
- ✅ Better performance due to thread pool usage
- ✅ Composable with continuation support
- ✅ Exception are captured in [System.AggregateException](System.AggregateException.md)



Threads:

- ✅ More control over thread lifecycle
- ✅ Direct access to thread properties
- ✅ Better for permanent background operations
- ❌ More complex error handling
- ❌ Manual resource management
- ❌ No built-in cancellation support
- ❌ Exceptions are not propogated
## Task uses
 ```cs
 // 1. For I/O-bound operations
async Task ReadFileAsync()
{
    await File.ReadAllTextAsync("file.txt");
}

// 2. When you need return values
Task<int> CalculateAsync() 
{
    return Task.Run(() => {
        // Complex calculation
        return result;
    });
}

// 3. For parallel operations that need composition
async Task ProcessDataAsync()
{
    var task1 = DoWorkAsync();
    var task2 = DoMoreWorkAsync();
    await Task.WhenAll(task1, task2);
}
```

## Thread uses
```cs
// 1. For CPU-bound operations that need precise control
Thread cpuThread = new Thread(() => {
    while (!stopRequested)
    {
        // Continuous CPU-intensive work
    }
});

// 2. When you need thread-specific properties
Thread customThread = new Thread(() => {
    // Work here
});
customThread.Priority = ThreadPriority.Highest;
customThread.IsBackground = true;

// 3. For long-running operations that need their own dedicated thread
Thread backgroundThread = new Thread(() => {
    while (true)
    {
        // Continuous monitoring or processing
        Thread.Sleep(1000);
    }
});
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
