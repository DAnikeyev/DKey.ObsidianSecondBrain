---
date_added: 2025-03-03
tags:
  - csharp
---
Up: [[Windows]]
___
 A **process** is an instance of a running program. It contains the program code and its current activity. Each process has its own memory space and system resources, such as file handles and security attributes. Processes are isolated from each other to ensure that they do not interfere with each other's operations, which enhances system stability and security. A process can contain multiple threads, which are the smallest units of execution within the process.
Process is defined by PID (Process ID)

Any process has separate virtual memory space, so it can't access memory of another process. Kernel data is also isolated for each process. 


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
