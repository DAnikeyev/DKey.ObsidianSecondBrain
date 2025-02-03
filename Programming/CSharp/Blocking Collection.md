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

Useful for implementing [Producer-Consumer Pattern](Producer-Consumer%20Pattern.md) 

## Features
 - Bounding:
 `BlockingCollection<int> collection = new BlockingCollection<int>(3);`
 - Blocking: This operation will block [[Thread]] until the item is available.
 `int item = collection.Take();`

>[!Info]
> BlockingCollection<\T> implements [IDisposable](IDisposable.md)


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
