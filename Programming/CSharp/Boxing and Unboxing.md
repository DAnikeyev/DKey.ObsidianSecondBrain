---
date_added: 2025-02-17
tags:
  - csharp
---
Up: [Value Type](Value%20Type.md)
___
 Boxing is the process of converting a [Value Type](Value%20Type.md) to the [Object](Object.md) or to any interface type implemented by this value type. 
In the following example, the integer variable `i` is _boxed_ and assigned to object `o`.
```cs
int i = 123;
// The following line boxes i.
object o = i;
```

The object `o` can then be unboxed and assigned to integer variable `i`:

```cs
o = 123;
i = (int)o;  // unboxing
```

### Performance

In relation to simple assignments, boxing and unboxing are computationally expensive processes. When a value type is boxed, a new object must be allocated and constructed. To a lesser degree, the cast required for unboxing is also expensive computationally
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
