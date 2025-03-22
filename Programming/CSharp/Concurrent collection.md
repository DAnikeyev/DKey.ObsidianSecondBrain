---
date_added: 2025-01-27
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
 >[!Info]
> GetEnumerator returns snapshot of collection at the time of call, so during iteration, if collection is modified, it will not throw exception but will not reflect the changes made after GetEnumerator call.

```cs
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
