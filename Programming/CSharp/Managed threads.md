---
date_added: 2025-03-18
tags:
  - csharp
---
Up: [Thread](Thread.md)
___
 Managed threads in .NET are threads that are controlled by the Common Language Runtime (CLR). They represent the abstraction provided by the .NET Framework over the underlying operating system (OS) threads. Here are some key points:

- Managed threads are created, managed, and scheduled by the CLR, which takes care of tasks like thread pooling, context switching, and garbage collection coordination.
- When you create a managed thread in C# (for example, through the System.Threading.[[Thread]] class or by using the [Task Parallel Library](Task%20Parallel%20Library.md)), the CLR maps that managed thread to an OS thread.
- Although managed threads rely on OS threads at a low level, the developer interacts with them in a managed, higher-level manner. The CLR handles many complexities such as resource management, exception handling, and synchronization.
- Due to this abstraction, the transition between user mode (where your managed code runs) and kernel mode (for operations like system calls or waiting on synchronization primitives) is mostly hidden from the developer.

If [Thread user-mode stack](Thread%20user-mode%20stack.md) is used, then thread is called to be run in user mode.
If [Thread kernel-mode stack](Thread%20kernel-mode%20stack.md) is used, then thread is called to be run in kernel mode.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
