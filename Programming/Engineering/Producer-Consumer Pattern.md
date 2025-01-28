---
date_added: 2025-01-28
tags:
  - design
---
Up: [Behavioral patterns](Behavioral%20patterns.md)
___
 ![](Pasted%20image%2020250128154616.png)

Shared memory access for multiple producers or consumers should be managed using either:
 - thread locks
 - lock-free thread safe operations
 - other ways of orchestrating like signaling with semaphores or volatile flags
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
