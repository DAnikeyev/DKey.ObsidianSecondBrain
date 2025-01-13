---
date_added: 2025-01-13
tags:
  - dotnet
---
Up: [CLR](CLR.md)
___
You can examine and disassemble the contents of an assembly with Microsoft’s ildasm tool. And with tools such as ILSpy or JetBrain’s dotPeek, you can go further and decompile the IL to C#.
## Properties

- Assemblies are implemented as .exe or .dll files. 
- Assemblies can be shared between application by being put in the Global Assembly Cache (GAC).
- Assemblies are only loaded into memory if they are required.
- You can use [[Reflection]]s to obtain information about assembly


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
