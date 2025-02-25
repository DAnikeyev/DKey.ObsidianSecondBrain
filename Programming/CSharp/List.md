---
date_added: 2025-01-27
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
Represents a strongly typed list of objects that can be accessed by index.
  
Public static members of this type are thread safe. Any instance members are not guaranteed to be thread safe.

>[!Info]
> While readonly collections can't be reassigned, the data they contain can be modified. If you need to guarantee the collection and its data are not modified, use [Concurrent Bag](Concurrent%20Bag.md) or an immutable collection.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
