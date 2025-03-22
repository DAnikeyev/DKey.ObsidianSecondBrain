---
date_added: 2025-03-21
tags:
  - csharp
---
Up: [Profiling in VS](Profiling%20in%20VS.md)
___
 1. **Allocations Graph:**
    
    - The Allocations graph shows the total allocated memory over time.
    - It helps you visualize memory allocation spikes and trends.
2. **Allocations by Type:**
    
    - This view lists the types of objects that have been allocated and the amount of memory they consume.
    - You can identify which object types are consuming the most memory.
3. **Allocations by Function:**
    
    - This view shows the functions that are responsible for object allocations.
    - It helps you pinpoint the code that is causing memory allocations.
4. **Call Tree:**
    
    - The Call Tree view provides a hierarchical view of the call stack, showing how functions call each other.
    - You can see which paths in your code lead to memory allocations.
5. **Source Code View:**
    
    - You can view the source code directly from the profiler report.
    - This allows you to see the exact lines of code that are responsible for allocations.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
