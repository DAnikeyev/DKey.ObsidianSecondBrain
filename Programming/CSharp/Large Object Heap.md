---
date_added: 2025-02-04
tags:
  - csharp
---
Up: [Garbage Collector](Garbage%20Collector.md)
___
 Objects that are larger than 85000 bytes are allocated in Large object heap. GC collects them using [Garbage Sweeping](Garbage%20Sweeping.md) strategy. There is exclusion for array of doubles, array of more then 1000 doubles is allocated on LOH.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
