---
date_added: 2025-03-16
tags:
  - csharp
---
Up: [Exception](Exception.md) [Task](Task.md)
___
If an exception is thrown in task, acquiring [[TaskResult]] or calling Task.Wait() will throw AggregateException with all Inner exceptions stored in `ReadOnlyCollection<Exception> InnerExceptions`
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
