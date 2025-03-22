---
date_added: 2025-02-18
tags:
  - csharp
---
Up: [Garbage Collector](Garbage%20Collector.md)
___
 The finalization queue is a data structure that holds references to objects that have a [Finalizer](Finalizer.md) method. It's a queue that holds objects that need to be finalized before they can be garbage collected. 
- Objects that have finalizers (destructors in C#) are automatically registered for finalization when allocated
- The queue is managed by the CLR's garbage collector (GC) and processed by a dedicated finalizer thread
- The GC identifies unreachable objects during collection and queues finalizable objects
- Finalizable objects are identified by the GC and queued when they become unreachable

Here's how the process works:

1. **Object Allocation**: An object is created and allocated memory on the managed heap.
    
2. **Object Usage**: The object is used in the program. During this time, it is referenced by one or more variables or other objects.
    
3. **Unreferenced State**: At some point, the object is no longer referenced by any part of the code, making it eligible for garbage collection.
    
4. **Finalization Queue**: If the object has a finalizer (destructor) defined, it is placed in the finalization queue by the garbage collector. The finalizer is a special method that is called to clean up unmanaged resources before the object is collected.
    
5. **Finalization**: The finalizer thread (or finalizer process) calls the finalizer method on the object. This allows the object to release any unmanaged resources it holds.
    
6. **Garbage Collection**: After the finalizer has run, the object is removed from the finalization queue and its memory is reclaimed by the garbage collector.
Finalization in C# occurs in conjunction with the garbage collection process. Here's a detailed breakdown of how finalization works in relation to garbage collection and threading:


## Example
```cs
        GC.Collect(); // This triggers the first GC cycle
        GC.WaitForPendingFinalizers(); // Wait for finalizers to complete
```

Objects with Fializers are not immediately collected by the GC. They are first placed in the Finalization Queue and are only collected in the next GC cycle after their Finalizer has been executed.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
