---
date_added: 2025-01-31
tags:
  - csharp
sr-due: 2025-04-05
sr-interval: 4
sr-ease: 279
---
Up: [Async-Await pattern](Async-Await%20pattern.md)
___
 `async` keyword is used to define an asynchronous method, which allows you to write code that can perform potentially long-running operations without blocking the calling thread. 
 When you mark a method with the `async` keyword, it enables the use of the `await` keyword within that method.
```cs
public async Task<int> GetDataAsync()
{
    // Simulate an asynchronous operation
    await Task.Delay(1000);
    return 42;
}
```
 
- Method Signature: An `async` method typically returns a [Task](Task.md) , `Task<T>`, or [ValueTask](ValueTask.md)`<T>`. If the method does not return a value, it returns `Task`. If it returns a value, it returns `Task<T>` or `ValueTask<T>`. For event handlers, which do not return a value, you can use `void`.
    
- **Awaiting Tasks**: Inside an `async` method, you can use the [[await]] keyword to pause the method's execution until the awaited task completes. This allows other operations to run concurrently.
    
- **Non-blocking**: The `async` keyword does not make a method run on a separate thread. Instead, it allows the method to be non-blocking, meaning it can yield control back to the caller while waiting for the awaited task to complete.
    
- **Control Flow**: When an `async` method is called, it begins executing synchronously until it hits an `await` expression. At that point, control returns to the caller, and the method resumes execution once the awaited task is complete.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
