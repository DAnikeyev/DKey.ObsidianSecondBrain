---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Project dependency](Project%20dependency.md)
___
 For referencing a compiled .NET assembly (DLL) that is not managed by NuGet, use the `<Reference>` element:
 ```cs
 <ItemGroup>
  <Reference Include="System.Data">
    <HintPath>..\lib\System.Data.dll</HintPath>
  </Reference>
</ItemGroup>
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
