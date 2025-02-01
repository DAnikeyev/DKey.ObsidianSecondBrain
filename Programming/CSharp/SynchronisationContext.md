---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [[Thread]]
___
 Provides the basic functionality for propagating a synchronization context in various synchronization models.
 The purpose of the synchronization model implemented by this class is to allow the internal asynchronous/synchronous operations of the common language runtime to behave properly with different synchronization models. This model also simplifies some of the requirements that managed applications have had to follow in order to work correctly under different synchronization environments.
 Can be used in Task to specify the synchronization context under which the continuation is executed.
 ```cs
 public class Example
{
    public async Task DemoContextBehavior()
    {
        // Captures the current context
        var originalContext = SynchronizationContext.Current;
        
        await Task.Run(() =>
        {
            // Inside Task.Run, there is no SynchronizationContext
            var backgroundContext = SynchronizationContext.Current; // null
            
            // Do work...
        });
        
        // Back on the original context
        Debug.Assert(SynchronizationContext.Current == originalContext);
    }
}
```

Current SyncronizationContext can be preserved for new [TaskScheduler](TaskScheduler.md) with method TaskScheduler.FromCurrentSynchronizationContext();

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
