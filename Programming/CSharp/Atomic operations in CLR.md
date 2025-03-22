---
date_added: 2025-03-18
tags:
  - csharp
---
Up: [Synchronisation](Synchronisation.md)
___
[[CLR]] guarantees that those types: Boolean,
Char, (S)Byte, (U)Int16, (U)Int32, (U)IntPtr, Single and [Reference Type](Reference%20Type.md) read-write operation will be atomic. 

Opposite of this can be seen in read-write of int64 where intermediate value like 0x0123456700000000 can be acquired during read-write operations.
This corruption is called **torn read**
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
