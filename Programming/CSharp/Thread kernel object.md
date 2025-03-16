---
date_added: 2025-03-15
tags:
  - csharp
---
Up: [Windows Thread](Windows%20Thread.md)
___
 is the internal representation used by the operating system to manage a thread. Every time a new thread is created (typically via functions such as CreateThread or beginthreadex), the kernel allocates a corresponding thread object. This object is at the heart of thread management and scheduling in Windows.
### Responsibilities
• Storing the thread's execution context, which consists of registers, pointers, and saved states used during context switching.  
• Maintaining the thread's state (such as running, waiting, or terminated) and scheduling priority so that the Windows scheduler can effectively decide when each thread should be executed.  
• Managing the thread’s associated resources, such as its kernel stack and other bookkeeping data necessary for its execution and context switching.  
• Handling synchronization: the kernel object can be used with various [Synchronisation Primitives](Synchronisation%20Primitives.md) like events, mutexes, and semaphores to coordinate the operation of multiple threads.  
• Tracking and managing handles: When a thread is created, a handle to its kernel object is returned. This handle allows user-level code to interact with the thread (e.g., waiting for it to complete or checking its status). Once all handles are closed and the thread has terminated, the system cleans up the kernel object.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
