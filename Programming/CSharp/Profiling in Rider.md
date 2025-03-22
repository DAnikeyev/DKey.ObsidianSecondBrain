---
date_added: 2025-03-19
tags:
  - csharp
---
Up: [Rider](Rider.md) [Performance](Performance.md)
___
 JetBrains Rider offers several profiling modes to help developers analyze and optimize their applications. Here's an overview of the main profiling modes available in Rider:

1. **Sampling**: This mode collects statistical data about your application's performance by periodically capturing the call stack. It has minimal impact on the application's performance and is suitable for identifying performance bottlenecks.
    
2. **Tracing**: This mode records every function call, providing detailed information about the execution flow. It is more accurate than sampling but can significantly slow down the application due to the overhead of recording each call.
    
3. **Line-by-Line Profiling**: This mode provides detailed insights into the execution time of each line of code. It's useful for pinpointing specific lines that are causing performance issues but can be quite resource-intensive.
    
4. **Timeline**: This mode captures a timeline of your application's activity, including CPU usage, I/O operations, and garbage collection events. It helps in understanding how different parts of the application interact over time.
    
5. **Memory Profiling**: This mode focuses on memory usage, helping you identify memory leaks and excessive memory consumption. It provides insights into object allocations and the memory footprint of your application.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
