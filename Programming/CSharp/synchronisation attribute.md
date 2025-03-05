---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [[Synchronisation Primitives]]
___

>[!Warning]
> Is For Framework, use lock/monitor/other ways of synchronization for .NET

 ```cs
 using System;
using System.Runtime.InteropServices;
using System.EnterpriseServices;

// Basic usage - makes the entire class synchronized
[Synchronization]
public class SynchronizedClass
{
    public void DoSomething()
    {
        // This method will be automatically synchronized
        Console.WriteLine("This access is thread-safe");
    }
}

// Specifying a specific synchronization option
[Synchronization(SynchronizationOption.Required)]
public class CustomSynchronizedClass
{
    public void DoSomething()
    {
        // This method will be synchronized according to the specified option
        Console.WriteLine("This access is thread-safe with custom synchronization");
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
