---
date_added: 2025-02-17
tags:
  - csharp
---
Up: [Application environment](Application%20environment.md)
___
 Represents an application domain, which is an isolated environment where applications execute. This class cannot be inherited.
## Methods

- CreateDomain()  Creates a new application domain.
- CreateInstance()  Creates a new instance of a specified type in the current application domain.
- ExecuteAssembly()  Executes the assembly contained in the specified file.
- GetAssemblies()  Gets the assemblies that have been loaded into the execution context of this application domain.
- Load()  Loads the assembly with a common object file format (COFF)-based image containing an emitted assembly.
- Unload() Unloads the specified application domain. ==Is Obsolete== use `Abort` instead

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
