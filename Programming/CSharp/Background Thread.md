---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Thread](Thread.md)
___
 A background thread does not prevent the application from terminating. If all foreground threads have finished executing, the application will close, and any remaining background threads will be stopped abruptly. Background threads are typically used for tasks that are not critical to the application's main functionality, such as logging or monitoring.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
