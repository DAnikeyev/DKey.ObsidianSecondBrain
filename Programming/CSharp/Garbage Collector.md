---
date_added: 2024-10-08
tags:
  - dotnet
---
Up: [CLR](CLR.md)
___
the garbage collector (GC) serves as an automatic memory manager. The garbage collector manages the allocation and release of memory for an application. 
### Benefits

- Frees developers from having to manually release memory.
- Allocates objects on the managed heap efficiently.
- Reclaims objects that are no longer being used, clears their memory, and keeps the memory available for future allocations. Managed objects automatically get clean content to start with, so their constructors don't have to initialize every data field.
- Provides memory safety by making sure that an object can't use for itself the memory allocated for another object.

### Fundamentals of memory

The following list summarizes important CLR memory concepts:

- Each process has its own, separate virtual address space. All processes on the same computer share the same physical memory and the page file, if there's one.
- By default, on 32-bit computers, each process has a 2-GB user-mode virtual address space.
- As an application developer, you work only with virtual address space and never manipulate physical memory directly. The garbage collector allocates and frees virtual memory for you on the managed heap.
- If you're writing native code, you use Windows functions to work with the virtual address space. These functions allocate and free virtual memory for you on native heaps.

Virtual memory can be in three states:

|State|Description|
|---|---|
|Free|The block of memory has no references to it and is available for allocation.|
|Reserved|The block of memory is available for your use and can't be used for any other allocation request. However, you can't store data to this memory block until it's committed.|
|Committed|The block of memory is assigned to physical storage.|
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
