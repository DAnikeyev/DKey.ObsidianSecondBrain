---
date_added: 2025-03-21
tags:
  - csharp
---
Up: [Profiling in VS](Profiling%20in%20VS.md)
___
 ### Analyzing CPU Usage Data:

1. **CPU Utilization Graph:**
    
    - The CPU Utilization graph shows the overall CPU usage over time.
    - You can see peaks and valleys indicating periods of high and low CPU activity.
2. **Functions and Call Tree:**
    
    - The Functions view lists the functions that consumed the most CPU time.
    - The Call Tree view shows the hierarchical call structure, helping you understand the call flow and identify bottlenecks.
3. **Hot Path:**
    
    - The Hot Path highlights the most expensive code paths in your application.
    - This helps you quickly identify where most of the CPU time is being spent.
4. **Source Code View:**
    
    - You can view the source code directly from the profiler report.
    - This allows you to see the exact lines of code that are consuming CPU time.n
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
