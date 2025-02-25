---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
 Concatenates two sequences.
 ```cs

    IEnumerable<string> query =
        cats.Select(cat => cat.Name).Concat(dogs.Select(dog => dog.Name));
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
