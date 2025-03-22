---
date_added: 2025-03-21
tags:
  - csharp
---
Up: [Profiling in VS](Profiling%20in%20VS.md)
___
The Instrumentation tool is similar to the [CPU usage VS profiler](CPU%20usage%20VS%20profiler.md) tool, except that it provides exact call counts and wall clock time instead of CPU utilization.

1. **Function Details:**
    
    - The profiler provides detailed information about each function, including the number of calls, inclusive time (time spent in the function and its callees), and exclusive time (time spent only in the function).
    - This data helps you identify which functions are consuming the most time.
2. **Call Tree:**
    
    - The Call Tree view shows the hierarchical call structure of your application, allowing you to see the sequence of function calls and their timings.
    - This helps you understand the flow of execution and identify performance hot spots.
3. **Modules and Functions:**
    
    - The profiler provides a breakdown of performance data by modules and functions.
    - You can see which modules and functions are contributing the most to the overall execution time.
4. **Source Code View:**
    
    - You can view the source code directly from the profiler report.
    - This allows you to see the exact lines of code that are consuming time and make targeted optimizations.
 5. **Function Details:**
    
    - The profiler provides detailed information about each function, including the number of calls, inclusive time (time spent in the function and its callees), and exclusive time (time spent only in the function).
    - This data helps you identify which functions are consuming the most time.
26. *Call Tree:**
    
    - The Call Tree view shows the hierarchical call structure of your application, allowing you to see the sequence of function calls and their timings.
    - This helps you understand the flow of execution and identify performance hot spots.
37. *Modules and Functions:**
    
    - The profiler provides a breakdown of performance data by modules and functions.
    - You can see which modules and functions are contributing the most to the overall execution time.
48. *Source Code View:**
    
    - You can view the source code directly from the profiler report.
    - This allows you to see the exact lines of code that are consuming time and make targeted optimizations.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
