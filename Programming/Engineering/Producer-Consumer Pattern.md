---
date_added: 2025-01-28
tags:
  - design
---
---
date_added: 2025-04-01
tags: []
---
Up: [[]]
___
 
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
Up: [Behavioral patterns](Behavioral%20patterns.md)
___
 ![](Pasted%20image%2020250128154616.png)

Shared memory access for multiple producers or consumers should be managed using either:
 - thread locks
 - lock-free thread safe operations
 - other ways of orchestrating like signaling with semaphores or volatile flags

Represented in C# by [IProducerConsumerCollection](IProducerConsumerCollection.md)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
