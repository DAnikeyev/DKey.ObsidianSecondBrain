---
date_added: 2025-03-21
tags:
  - csharp
---
Up: [Profiling in VS](Profiling%20in%20VS.md)
___
Asynchronous events are organized into activities chronologically. Each displays its start time, end time, and duration.

Each row that corresponds to a task is labeled in the Name column. For any task name that can't be resolved, a Task in label appears. It's followed by the name of the method the task occurs within. If an asynchronous activity doesn't complete within the collection session, an Incomplete label appears in the End Time column.

To further investigate a specific task or activity, right-click the row. Then select Go To Source File to see where in your code that activity happened.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
