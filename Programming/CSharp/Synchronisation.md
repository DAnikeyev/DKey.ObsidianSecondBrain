---
date_added: 2025-03-17
tags:
  - csharp
---
Up: [Asynchronous programming](Asynchronous%20programming.md)
___
 For [Thread](Thread.md)s synchronisation Is handling correct interaction of multiple threads to a shared resource. Usually [Synchronisation Primitives](Synchronisation%20Primitives.md) are used to achieve this.

Static methods of [BCL](BCL.md) are thread-safe, but instance methods are not.
## Locking

 - [lock](lock.md)
 - [Monitor](Monitor.md)
 - [Mutex](Mutex.md)
 - [[Semaphore]]

## Lock-free

 - [Concurrent collection](Concurrent%20collection.md)
 - [volatile](volatile.md) and Thread.MemoryBarrier
 - [Interlocked](Interlocked.md)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
