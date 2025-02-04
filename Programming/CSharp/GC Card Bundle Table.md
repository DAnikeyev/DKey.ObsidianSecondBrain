---
date_added: 2025-02-04
tags:
  - csharp
---
Up: [GC Card table](GC%20Card%20table.md)
___
 Is a Card Table for Card Table. 1 bit represents 1024 card bit (256KB of target memory for x64)
 1 cell = 4 bytes = 8MB of memory
During Gen0 collecting: 
- Check Card Bundle Table with marks 
- For Marked Card Tables check bytes with marks
- For Marked memory check all object links to Gen0.
- If object has no links (and no links inside Gen0), clean it.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
