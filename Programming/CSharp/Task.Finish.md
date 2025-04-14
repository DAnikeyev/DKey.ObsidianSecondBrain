---
date_added: 2025-04-03
tags:
  - csharp
---
Up: [[Task]]
___
 If task is executed, in the end method Finish is called

## Stage 1
 - If no child tasks, go to stage 2
## Stage 2
 - Take exceptions from child tasks
 - Set Task completion status
## Stage 3
 - Set delegate pointer to null so that it is collected by [Garbage Collector](Garbage%20Collector.md)
 - Update parent, about completion of this task
 - If that's the last child task of the parrent call its FinishStageTwo


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
