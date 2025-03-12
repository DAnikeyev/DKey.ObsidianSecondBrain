---
date_added: 2025-03-10
tags:
  - csharp
---
Up: [Value Type](Value%20Type.md)
___
 If value-type is a field of a class, it stored on a heap
```cs
class Person
{
    public int Age;        // Value type (4 bytes)
    public DateTime Birth; // Value type (8 bytes)
    public string Name;    // Reference type (pointer size: 4 or 8 bytes depending on architecture)
}
```


The memory layout on the heap would be:
```cs
[Object Header (8 or 16 bytes)] + [Method Table Pointer (4 or 8 bytes)] + [Age (4 bytes)] + [Birth (8 bytes)] + [Name reference (4 or 8 bytes)]
```

>[!Info]
> Value-types here are not boxed - it's important optimisation of .net!
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
