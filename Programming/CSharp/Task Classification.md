---
date_added: 2025-04-02
tags:
  - csharp
---
Up: [Task](Task.md)
___
# IsLongRunning

 - part of  [[TaskCreationOptions]]
 - it suggests to the Task Scheduler that it might be beneficial to create a new thread for this task, rather than queuing it to the thread pool.
# Task type
 - Delegate task (Action, Func, etc)
 - Promises (Tasks without action)
 - Influence [TaskStatus](TaskStatus.md) options, Promises only have `WaitingForActivation` and various Completed status.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
