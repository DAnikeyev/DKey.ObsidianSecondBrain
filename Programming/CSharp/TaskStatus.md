---
date_added: 2025-01-30
tags:
  - csharp
---
Up: [Task](CSharp/Task.md)
___
 Status property returns this enum value.

|Name|Value|Description|
|---|---|---|
|Created|0|The task has been initialized but has not yet been scheduled.|
|WaitingForActivation|1|The task is waiting to be activated and scheduled internally by the .NET infrastructure.|
|WaitingToRun|2|The task has been scheduled for execution but has not yet begun executing.|
|Running|3|The task is running but has not yet completed.|
|WaitingForChildrenToComplete|4|The task has finished executing and is implicitly waiting for attached child tasks to complete.|
|RanToCompletion|5|The task completed execution successfully.|
|Canceled|6|The task acknowledged cancellation by throwing an OperationCanceledException with its own CancellationToken while the token was in signaled state, or the task's CancellationToken was already signaled before the task started executing. For more information, see [Task Cancellation](https://learn.microsoft.com/en-us/dotnet/standard/parallel-programming/task-cancellation).|
|Faulted|7|The task completed due to an unhandled exception.|
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
