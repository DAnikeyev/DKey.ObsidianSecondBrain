---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [[Synchronisation]]
___
-  [System.Threading.Mutex](https://learn.microsoft.com/en-us/dotnet/api/system.threading.mutex), which grants exclusive access to a shared resource. The state of a mutex is signaled if no thread owns it.
- [System.Threading.Semaphore](https://learn.microsoft.com/en-us/dotnet/api/system.threading.semaphore), which limits the number of threads that can access a shared resource or a pool of resources concurrently. The state of a semaphore is set to signaled when its count is greater than zero, and nonsignaled when its count is zero.
- [System.Threading.EventWaitHandle](https://learn.microsoft.com/en-us/dotnet/api/system.threading.eventwaithandle), which represents a thread synchronization event and can be either in a signaled or unsignaled state.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
