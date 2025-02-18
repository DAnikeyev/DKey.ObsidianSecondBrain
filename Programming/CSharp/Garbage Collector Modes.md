---
date_added: 2025-02-18
tags:
  - csharp
---
Up: [Garbage Collector](Garbage%20Collector.md)
___

## Workstation

- GC is more frequent but faster.
- Unoptimal, due to restriction to keep UI responsive.
## Server
- GC is slower and rarer
- Total collecting time is faster
- Will consume more memory.
- 
>[!Info]
> There is also separation for concurrent and non-concurrent mode, but concurrent mode is not fully concurrent. Concurrent mode tries to collect without pausing all thread, but takes a lot of resources to support that.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
