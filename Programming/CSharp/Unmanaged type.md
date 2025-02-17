---
date_added: 2025-02-17
tags:
  - csharp
---
Up: [CTS](CTS.md)
___
 A type is an **unmanaged type** if it's any of the following types:

- `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `nint`, `nuint`, `char`, `float`, `double`, `decimal`, or `bool`
- Any [Enumeration type](Enumeration%20type.md)
- Any [Pointer type](Pointer%20type.md)
- A [Tuple](Tuple.md) whose members are all of an unmanaged type
- Any user-defined [Struct](Struct.md) type that contains fields of unmanaged types only.
### Key Differences

- **Scope**: All unmanaged types are [Value Type](Value%20Type.md), but not all value types are unmanaged. For example, a struct containing a reference type field is a value type but not an unmanaged type.
    
- **Memory Management**: Value types are managed by the .NET runtime, while unmanaged types are not. This distinction is important for scenarios requiring precise control over memory.
    
- **Use Cases**: Unmanaged types are particularly useful for interoperability with native code and performance-critical applications, whereas value types are commonly used for their efficiency and simplicity in everyday programming.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
