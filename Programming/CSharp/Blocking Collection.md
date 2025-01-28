---
date_added: 2025-01-27
tags:
  - csharp
---
Up: [Concurrent collection](Concurrent%20collection.md)
___
 Can specify FIFO or LIFO order. 
 ```cs
 // Default FIFO behavior using ConcurrentQueue<T>
BlockingCollection<int> fifoCollection = new BlockingCollection<int>();

// LIFO behavior using ConcurrentStack<T>
BlockingCollection<int> lifoCollection = new BlockingCollection<int>(new ConcurrentStack<int>());
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
