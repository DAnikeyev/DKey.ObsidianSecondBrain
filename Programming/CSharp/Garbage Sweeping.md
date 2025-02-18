---
date_added: 2025-02-04
tags:
  - csharp
---
Up: [Garbage Collecting Strategies](Garbage%20Collecting%20Strategies.md)
___
 Is a strategy of moving unused gaps to the memory, available for new allocation. Suitable for Large objects, as Large gaps are more likely to be suitable for [[allocation]].

## Algorithm
- Traverse heap Freeing memory for unmarked objects
- Add freed memory to the list of available memory
- Combine adjacent gaps
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
