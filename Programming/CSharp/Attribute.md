---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Reflection](Reflection.md), [Other CSharp Features](Other%20CSharp%20Features.md)
___
 Attributes add metadata to your program.
- You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.
- Attributes can accept arguments in the same way as methods and properties.
- You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.
- Your program can examine its own metadata or the metadata in other programs by using [Reflection](Reflection.md).

>[!Info]
>The C# keywords `protected` and `internal` have no meaning in Intermediate Language (IL) and are not used in the reflection APIs. The corresponding terms in IL are _Family_ and _Assembly_. To identify an `internal` method using reflection, use the [IsAssembly](https://learn.microsoft.com/en-us/dotnet/api/system.reflection.methodbase.isassembly) property. To identify a `protected internal` method, use the [IsFamilyOrAssembly](https://learn.microsoft.com/en-us/dotnet/api/system.reflection.methodbase.isfamilyorassembly).
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
