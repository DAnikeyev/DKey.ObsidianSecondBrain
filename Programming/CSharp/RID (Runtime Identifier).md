---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Application environment](Application%20environment.md)
___
 RID values are used to identify target platforms where the application runs. The following values are examples of RIDs: `linux-x64`, `win-x64`, or `osx-x64`. For the packages with native dependencies, the RID designates on which platforms the package can be restored. When NuGet restores packages, it tries to find an exact match for the specified runtime. If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
