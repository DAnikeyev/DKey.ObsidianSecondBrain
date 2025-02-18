---
date_added: 2025-02-18
tags:
  - csharp
---
Up: [Garbage Collector](Garbage%20Collector.md)
___
 The finalization queue is a data structure that holds references to objects that have a finalizer method. It's a queue that holds objects that need to be finalized before they can be garbage collected. 
- Objects that have finalizers (destructors in C#) are automatically registered for finalization when allocated
- The queue is managed by the CLR's garbage collector (GC) and processed by a dedicated finalizer thread
- The GC identifies unreachable objects during collection and queues finalizable objects
- Finalizable objects are identified by the GC and queued when they become unreachable
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
