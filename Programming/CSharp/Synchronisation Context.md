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

It is part of [Thread Execution Context](Thread%20Execution%20Context.md) but it's does not “flow” across await points.


## Post and Send
- **Asynchronous Execution**: The `Post` method is used to queue a delegate for execution on the synchronization context asynchronously. This means that the method returns immediately, and the delegate is executed at some point in the future.
    
- **Usage**: It's typically used when you want to update the UI from a background thread without blocking the calling thread.
    
- **Example**:
```cs
SynchronizationContext context = SynchronizationContext.Current;

// Assume this is called from a background thread
context.Post(state =>
{
    // Update UI elements here
    myLabel.Text = "Updated from background thread";
}, null);
```

- **Synchronous Execution**: The `Send` method is used to dispatch a delegate to the synchronization context for synchronous execution. This means that the calling thread is blocked until the delegate has been executed.
    
- **Usage**: It's used when you need to ensure that a piece of code runs on the synchronization context and you need to wait for it to complete before continuing.
    
- **Example**:
```cs
SynchronizationContext context = SynchronizationContext.Current;

// Assume this is called from a background thread
context.Send(state =>
{
    // Update UI elements here
    myLabel.Text = "Updated from background thread";
}, null);
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
