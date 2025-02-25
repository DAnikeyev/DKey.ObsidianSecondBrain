---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___

 `true` if every element of the source sequence passes the test in the specified predicate, or if the sequence is empty; otherwise, `false`.

```cs
public static bool All<TSource>(this System.Collections.Generic.IEnumerable<TSource> source, Func<TSource,bool> predicate);
```

 ```cs
    bool allStartWithB = pets.All(pet => pet.Name.StartsWith("B"));
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
