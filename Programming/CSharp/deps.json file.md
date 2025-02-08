---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Compilation process](Compilation%20process.md)
___

- After resolving and restoring dependencies based on the csproj references, the build process generates a .deps.json file. This file lists all the dependencies (including their versions and the paths to their assemblies) that your application requires at runtime. 
-  The .deps.json file is used by the .NET Core runtime to locate and load these dependencies during the startup of your application. It serves as a manifest for dependency resolution at runtime.
- It reflects the information specified in your csproj file, along with additional metadata needed by the runtime, but it is entirely generated automatically and not meant to be edited or managed manually.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
