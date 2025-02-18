---
date_added: 2025-02-04
tags:
  - csharp
---
Up: [Garbage Collecting Strategies](Garbage%20Collecting%20Strategies.md)
___
 Is a strategy of moving used object closer to each other, performing defragmentation. Suitable for small object as moving large objects can be expensive.

## Algorithm

- Commit more memory if needed
- Relocate objects to the left.
- While traversing heap counting gaps offset and changing all pointers to the new location. Update all links for built graph
- While traversing, also use [GC Card table](GC%20Card%20table.md) to track older-to-younger links. Update all links.
- Traverse stack to update links for objects, that are not [Unmanaged type](Unmanaged%20type.md), update links there
- Update links from [[FinalizationQueue]]
- Update links from [[Handle table]]
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
