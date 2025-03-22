---
date_added: 2025-03-21
tags:
  - csharp
---
Up: [Profiling in VS](Profiling%20in%20VS.md)
___
>[!Info]
>You have  to manually take snapshots to analyze memory usage in Visual Studio. 


 1. **Memory Usage Graph:**
    
    - The Memory Usage graph shows the total memory usage over time.
    - It helps you visualize memory allocation patterns and identify spikes in memory usage.
2. **Snapshots:**
    
    - Each snapshot provides detailed information about the memory usage at a specific point in time.
    - You can compare snapshots to see how memory usage changes over time or after specific operations.
3. **Heap Size and Objects:**
    
    - The profiler provides information about the size of the managed heap and the number of objects in memory.
    - This helps you understand the allocation and retention of objects.
4. **Largest Object Types:**
    
    - The profiler lists the types of objects that consume the most memory.
    - This helps you identify which objects are contributing to high memory usage.
5. **Object Retention Graph:**
    
    - The Object Retention Graph shows the relationships between objects and how they are retained in memory.
    - This helps you identify memory leaks and objects that are not being garbage collected.
6. **Detailed View:**
    
    - You can drill down into specific objects and see their allocation paths, sizes, and references.
    - This detailed view helps you pinpoint the exact source of memory issues.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
