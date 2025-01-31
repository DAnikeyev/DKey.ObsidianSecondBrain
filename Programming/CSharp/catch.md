---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Exception handling statements](Exception%20handling%20statements.md)
___
When Exception is thrown CLR search for a catch block that can handle this exception. up the call stack. If no `catch` block is found, the CLR terminates the executing thread.

 ```cs
try
{
    ProcessShapes(shapeAmount);
}
catch (Exception e)
{
    LogError(e, "Shape processing failed.");
    throw;
}
```

>[!Info]
> `throw;` preserves the original stack trace of the exception, which is stored in the [Exception.StackTrace](https://learn.microsoft.com/en-us/dotnet/api/system.exception.stacktrace#system-exception-stacktrace) property. Opposite to that, `throw e;` updates the [StackTrace](https://learn.microsoft.com/en-us/dotnet/api/system.exception.stacktrace#system-exception-stacktrace) property of `e`.


## Multiple catch blocks
 ```csharp
 try
{
    var result = await ProcessAsync(-3, 4, cancellationToken);
    Console.WriteLine($"Processing succeeded: {result}");
}
catch (ArgumentException e)
{
    Console.WriteLine($"Processing failed: {e.Message}");
}
catch (OperationCanceledException)
{
    Console.WriteLine("Processing is cancelled.");
}
 ```
Only 1 catch block is executed, the first one that can handle the exception.


## When exception filter
 ```csharp
 try
{
    var result = Process(-3, 4);
    Console.WriteLine($"Processing succeeded: {result}");
}
catch (Exception e) when (e is ArgumentException || e is DivideByZeroException)
{
    Console.WriteLine($"Processing failed: {e.Message}");
}
 ```


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
