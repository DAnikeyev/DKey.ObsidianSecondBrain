---
date_added: 2025-02-11
tags:
  - csharp
---
Up: [Compilation process](Compilation%20process.md)
___
 When restoring [Nuget package](Nuget%20package.md) for example using [command dotnet restore](command%20dotnet%20restore.md)  the NuGet package manager downloads the specified package and its dependencies from the NuGet repository. The packages are stored in a global cache (typically located at `~/.nuget/packages`).
### dotnet restore command

1. **Dependency Resolution**: The `dotnet restore` command resolves the dependencies specified in your project file. It ensures that all required packages are downloaded and available in the global cache.
    
2. **Creating a Lock File**: A lock file (`project.assets.json`) is generated in the `obj` directory. This file contains a detailed list of all resolved dependencies and their versions. It ensures consistent builds by locking the dependencies to specific versions.

## Package Restore behavior

Package Restore tries to install all package dependencies to the state that matches the `<PackageReference>`s in a project file, such as _.csproj_, or `<package>`s in a packages.config file.
packages.config is the old way of managing packages in .NET projects. It is still supported in .NET Core, but it is recommended to use PackageReference in .csproj files.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
