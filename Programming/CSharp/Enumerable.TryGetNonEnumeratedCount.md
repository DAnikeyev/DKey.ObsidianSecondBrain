---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
 Attempts to determine the number of elements in a sequence without forcing an enumeration.
 ```csharp
 public static bool TryGetNonEnumeratedCount<TSource>(this System.Collections.Generic.IEnumerable<TSource> source, out int count);
 ```
The method performs a series of type tests, identifying common subtypes whose count can be determined without enumerating. This includes [ICollection](ICollection.md), and internal types used in the LINQ implementation.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
