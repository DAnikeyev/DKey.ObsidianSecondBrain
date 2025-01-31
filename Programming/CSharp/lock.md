---
date_added: 2025-01-30
tags:
  - csharp
---
Up: [[CSharp Statement]]
___
 The `lock` statement acquires the mutual-exclusion lock for a given object, executes a statement block, and then releases the lock.
 ```
lock (x)
{
    // Your code...
}
```
When `x` is known at compile-time to be of the type [System.Threading.Lock](https://learn.microsoft.com/en-us/dotnet/api/system.threading.lock), it's precisely equivalent to:
```cs
using (x.EnterScope())
{
    // Your code...
}
```

The object returned by [Lock.EnterScope()](https://learn.microsoft.com/en-us/dotnet/api/system.threading.lock.enterscope#system-threading-lock-enterscope) is a [Ref Struct](Ref%20Struct.md) that includes a `Dispose()` method.

Other than that, the `lock` statement is a shorthand for:

```cs
object __lockObj = x;
bool __lockWasTaken = false;
try
{
    System.Threading.Monitor.Enter(__lockObj, ref __lockWasTaken);
    // Your code...
}
finally
{
    if (__lockWasTaken) System.Threading.Monitor.Exit(__lockObj);
}
```

Starting from C# 13 and dotnet 9 a dedicated object instance of the [System.Threading.Lock](https://learn.microsoft.com/en-us/dotnet/api/system.threading.lock) type for best performance should be used.

## Example
```cs
using System;
using System.Threading;

class Program
{
    private static readonly object _lockObject = new object();
    private static int _sharedResource = 0;

    static void Main()
    {
        Thread thread1 = new Thread(IncrementResource);
        Thread thread2 = new Thread(IncrementResource);

        thread1.Start();
        thread2.Start();

        thread1.Join();
        thread2.Join();

        Console.WriteLine($"Final value of shared resource: {_sharedResource}");
    }

    private static void IncrementResource()
    {
        for (int i = 0; i < 1000; i++)
        {
            lock (_lockObject)
            {
                _sharedResource++;
            }
        }
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
