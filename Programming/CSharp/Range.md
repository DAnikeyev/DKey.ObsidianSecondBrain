---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
 Represents a range that has start and end indexes.
 ```cs
 int[] someArray = new int[5] { 1, 2, 3, 4, 5 };
int[] subArray1 = someArray[0..2];               // { 1, 2 }
int[] subArray2 = someArray[1..^0];              // { 2, 3, 4, 5 }
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
