---
date_added: 2025-02-18
tags:
  - csharp
---
Up: [Garbage Collector](Garbage%20Collector.md)
___
## Triggers
- [Small Object Heap](Small%20Object%20Heap.md) or [Large Object Heap](Large%20Object%20Heap.md) used most available space
- Manually
- Fragmentation is too big

## Marking phase
Starting with roots do [[Depth-First-Search]] to visit all accessable objects.
##### Roots:
 - Static objects
 - Local variables in scope, based on [Eager root collection](Eager%20root%20collection.md) table
 - CPU registers
 - Pinned objects
 - Ready for Finalization objects.
 - GC Handles
## Planning phase

- [Garbage Compacting](Garbage%20Compacting.md) is preparing to be done so that [Garbage Collector](Garbage%20Collector.md) can decide to use it or [Garbage Sweeping](Garbage%20Sweeping.md)
- Listing  groups of objects into Plugs and Gaps
- On fly building [[Binary-Search-Tree]] to find and replace objects fast.
![Compacting is choosed if Generation is big and scarse](Pasted%20image%2020250218065228.png)
## Collecting

Using [Garbage Sweeping](Garbage%20Sweeping.md) or [Garbage Compacting](Garbage%20Compacting.md).

>[!Info]
> [Large Object Heap](Large%20Object%20Heap.md) don't use [Garbage Compacting](Garbage%20Compacting.md) unless requested

## Generation changes

Objects aren't moved between generations. Instead, ranges of generations are moved. Checking generation just compare object adress with those intervals.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
