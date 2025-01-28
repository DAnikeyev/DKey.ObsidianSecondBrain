---
date_added: 2025-01-27
tags:
  - csharp
---
Up: [Concurrent collection](Concurrent%20collection.md)
___
ConcurrentQueue\<T> and ConcurrentStack\<T> are completely lock-free in this way. They will never take a lock, but they may end up spinning and retrying an operation when faced with contention (when the CAS operations fail).
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
