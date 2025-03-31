---
date_added: 2025-03-24
tags:
  - csharp
---
Up: [Windows Thread](Windows%20Thread.md)
___
 A thread scheduler ensures all active threads are allocated appropriate execution time, and that threads that are waiting or blocked (for instance, on an exclusive lock or on user input)  do not consume CPU time.
Scheduling threads is a work delegated to [[OS]] 

>[!Important]
> Under Windows, a time-slice is typically in the tens-of-milliseconds region — much larger than the CPU overhead in actually switching context between one thread and another (which is typically in the few-microseconds region).
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
