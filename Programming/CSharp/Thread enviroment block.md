---
date_added: 2025-03-15
tags:
  - csharp
---
Up: [Windows Thread](Windows%20Thread.md)
___
is a per-thread data structure that stores crucial runtime information for each thread in a process.

Here’s an overview of its responsibilities:

• Data Management:  
The TEB holds thread-local storage (TLS) data, which includes variables unique to the thread. This mechanism lets each thread maintain its own state independently of others.

• Exception Handling:  
It stores exception-handling information, such as pointers to structured exception handlers. This allows for proper handling of exceptions that occur during a thread's execution.

• Stack Information:  
The TEB contains details about the thread’s stack, including the boundaries (e.g., stack base and limit). With this information, the system can monitor and protect against stack overflows or improper usage.

• Performance Counters and Thread-Specific Data:  
It can also include performance-related counters, error codes (such as the last error value), and other thread-specific data that might be required during the lifetime of the thread.

• Interfacing with the Operating System:  
The TEB connects to other fundamental structures like the Process Environment Block (PEB), creating a bridge between the thread-specific context and the wider process context. This interconnection is essential for the operating system to manage and coordinate multiple threads within the same process.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
