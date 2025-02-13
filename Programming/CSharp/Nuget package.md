---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Project dependency](Project%20dependency.md)
___
Put simply, a NuGet package is a single ZIP file with the `.nupkg` extension that contains compiled code (DLLs), other files related to that code, and a descriptive manifest that includes information like the package's version number.

[Nuget.org](Nuget.org.md) is a public package repository that hosts thousands of free and open-source packages. You can use the `dotnet` CLI to install packages from NuGet.org or other sources.

## References
You can run your own server for a private nuget source: https://learn.microsoft.com/en-us/nuget/hosting-packages/nuget-server


To include a NuGet package, use the `<PackageReference>` element. You can specify the package name and version:

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="13.0.1" />
</ItemGroup>
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
