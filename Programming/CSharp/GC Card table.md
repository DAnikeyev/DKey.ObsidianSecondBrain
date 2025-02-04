---
date_added: 2025-02-04
tags:
  - csharp
---
Up: [Garbage Collector](Garbage%20Collector.md)
___
 To monitor links between generation (and understanding which objects are unused) Card tables are used to track older-to-younger links
 ![](Pasted%20image%2020250204203216.png)

1 bit is marked if represented memory (128 byte in x86 and 256 byte in x64) has object with link to younger generation. Marking is happening for whole byte 0xFF so that represent 1-2KB of memory
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
