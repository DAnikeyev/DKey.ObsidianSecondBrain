---
date_added: 2025-01-31
tags:
  - csharp
sr-due: 2025-04-05
sr-interval: 4
sr-ease: 276
---
Up: [Async-Await pattern](Async-Await%20pattern.md) 
___
 `await` keyword is used in  [Asynchronous programming](Asynchronous%20programming.md) to pause the execution of an [[async]] method until the awaited [Task](Task.md) completes. It allows the method to be non-blocking, meaning it can continue executing other code or return control to the caller while waiting for the task to finish.
## [[Thread]] management

### When thread is released
- **When awaiting an incomplete task**: If you `await` a task that isn't completed yet, the current thread is released back to the thread pool and can be used for other work.
- **When awaiting I/O-bound operations**: Operations like network requests, file I/O, etc., are typically executed without blocking threads.
### When thread is not released
 - **When awaiting an already completed task**: If the task is already completed when you `await` it, the execution continues on the same thread without any context switch.
 - **When using `ConfigureAwait(false)`**: This explicitly tells the runtime not to return to the original context.

## The State Machine Transformation

When you use the `await` keyword in C#, a sophisticated mechanism is triggered that involves state machines, thread management, and synchronization contexts. 

#### Code
```cs
async Task<string> GetDataAsync()
{
    var result1 = await Step1Async();
    var result2 = await Step2Async(result1);
    return result2;
}
```

#### StateMachine:
```cs
Task<string> GetDataAsync()
{
    var stateMachine = new GetDataAsyncStateMachine();
    stateMachine.builder = AsyncTaskMethodBuilder<string>.Create();
    stateMachine.state = -1; // Initial state
    stateMachine.MoveNext();
    return stateMachine.builder.Task;
}

struct GetDataAsyncStateMachine : IAsyncStateMachine
{
    public AsyncTaskMethodBuilder<string> builder;
    public int state;
    
    private string result1;
    private string result2;
    private TaskAwaiter<string> awaiter1;
    private TaskAwaiter<string> awaiter2;
    
    public void MoveNext()
    {
        string result = null;
        try
        {
            bool continueExecution = true;
            
            if (state == -1) // Initial call
            {
                // Start the first awaitable operation
                awaiter1 = Step1Async().GetAwaiter();
                
                if (!awaiter1.IsCompleted)
                {
                    state = 0; // Remember we're waiting for Step1
                    builder.AwaitUnsafeOnCompleted(ref awaiter1, ref this);
                    continueExecution = false; // Exit MoveNext, we'll resume when Step1 completes
                }
            }
            
            if (continueExecution && state <= 0)
            {
                // Step1 is complete, get the result
                result1 = awaiter1.GetResult();
                
                // Start the second awaitable operation
                awaiter2 = Step2Async(result1).GetAwaiter();
                
                if (!awaiter2.IsCompleted)
                {
                    state = 1; // Remember we're waiting for Step2
                    builder.AwaitUnsafeOnCompleted(ref awaiter2, ref this);
                    continueExecution = false; // Exit MoveNext, we'll resume when Step2 completes
                }
            }
            
            if (continueExecution)
            {
                // Step2 is complete, get the result
                result2 = awaiter2.GetResult();
                
                // We're done, return the final result
                result = result2;
                state = -2; // Finished
            }
        }
        catch (Exception ex)
        {
            state = -2; // Finished with an exception
            builder.SetException(ex);
            return;
        }
        
        if (state == -2)
        {
            builder.SetResult(result);
        }
    }
    
    public void SetStateMachine(IAsyncStateMachine stateMachine) { /* Implementation */ }
}
```

## Advanced Concepts

1. **Nested Awaits**: When you have nested awaits, they create nested state machines.
    
2. **The Awaitable.GetAwaiter() Method**: This returns an object that provides the core await functionality.
    
3. **Task Unwrapping**: When you await a `Task<Task<T>>`, C# automatically unwraps it to a `Task<T>`.
    
4. **Exception Handling**: Exceptions in async methods are captured and stored in the resulting Task, allowing for both sync and async error handling. See [System.AggregateException](System.AggregateException.md)
    
5. **Cancellation Integration**: The async/await infrastructure works seamlessly with [Cancellation Token](Cancellation%20Token.md)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
