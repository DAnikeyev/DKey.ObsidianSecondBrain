---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
 Like [Span T](Span%20T.md) `Memory<T>` represents a continuous region of memory, Unlike [[Span T]]  `Memory<T>` is not a [Ref Struct](Ref%20Struct.md) and can be placed on the managed heap

As span is allocated on stack, It's more suitable for short-term storing  data locally for the current scope, while `Memory<T>` is more suitable for long-term storing data that needs to be passed around.

| Method     | Mean       | Error     | StdDev   | Allocated |
|----------- |-----------:|----------:|---------:|----------:|
| Span       |   329.1 us |  16.80 us |  2.60 us |     313 B |
| CopyArray  | 1,359.3 us | 229.18 us | 59.52 us | 4000337 B |
| IndexArray |   477.1 us |  12.78 us |  3.32 us |     313 B |
| Memory     |   327.9 us |  21.81 us |  5.66 us |     313 B |

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
