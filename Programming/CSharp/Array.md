---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
 allows to store a multiple item of the same type 
 ```cs
 type[] arrayName;
```

Array.CreateInstance can be used to create arrays dynamically in runtime.
Implements [[IEnumerable]] and [[ICollection]] and [[ILIst]] interfaces.

```cs
## Nullable type:
```cs
type?[] arrayName; // non nullable array of nullable element types.
type[]? arrayName; // nullable array of non-nullable element types.
type?[]? arrayName; // nullable array of nullable element types.
```

Multi-dimensional arrays:
```cs
int[,] matrix = new int[3, 3];
int[,,] cube = new int[3, 3, 3];
```

Jagged arrays:
```cs
int[][] jagged = new int[3][];
jagged[0] = new int[3];
jagged[1] = new int[2];
```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
