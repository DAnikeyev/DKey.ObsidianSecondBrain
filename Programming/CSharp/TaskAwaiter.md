---
date_added: 2025-03-24
tags:
  - csharp
---
Up: [[Task]]
___
Represents an object that waits for the completion of an asynchronous task and provides a parameter for the result. used in StateMachine of [Async-Await pattern](Async-Await%20pattern.md)


>[!Info]
> Intended to be used only by compiler

## Properties

|   |   |
|---|---|
|[IsCompleted](https://learn.microsoft.com/en-us/dotnet/api/system.runtime.compilerservices.taskawaiter-1.iscompleted?view=net-9.0#system-runtime-compilerservices-taskawaiter-1-iscompleted)|This API supports the product infrastructure and is not intended to be used directly from your code.<br><br>Gets a value that indicates whether the asynchronous task has completed.|

## Methods

|   |   |
|---|---|
|[GetResult()](https://learn.microsoft.com/en-us/dotnet/api/system.runtime.compilerservices.taskawaiter-1.getresult?view=net-9.0#system-runtime-compilerservices-taskawaiter-1-getresult)|Ends the wait for the completion of the asynchronous task.|
|[OnCompleted(Action)](https://learn.microsoft.com/en-us/dotnet/api/system.runtime.compilerservices.taskawaiter-1.oncompleted?view=net-9.0#system-runtime-compilerservices-taskawaiter-1-oncompleted\(system-action\))|This API supports the product infrastructure and is not intended to be used directly from your code.<br><br>Sets the action to perform when the [TaskAwaiter<TResult>](https://learn.microsoft.com/en-us/dotnet/api/system.runtime.compilerservices.taskawaiter-1?view=net-9.0) object stops waiting for the asynchronous task to complete.|
|[UnsafeOnCompleted(Action)](https://learn.microsoft.com/en-us/dotnet/api/system.runtime.compilerservices.taskawaiter-1.unsafeoncompleted?view=net-9.0#system-runtime-compilerservices-taskawaiter-1-unsafeoncompleted\(system-action\))|This API supports the product infrastructure and is not intended to be used directly from your code.<br><br>Schedules the continuation action for the asynchronous task associated with this awaiter.|
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
