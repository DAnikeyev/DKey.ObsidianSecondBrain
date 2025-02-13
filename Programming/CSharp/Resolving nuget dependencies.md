---
date_added: 2025-02-11
tags:
  - csharp
---
Up: [Restoring packages](Restoring%20packages.md)
___
 Part of [Restoring packages](Restoring%20packages.md) is making a list of all dependencies with respective versions which are required for application to work.
 The list is the file `project.assets.json` file in the `obj` directory.
 
 ### Steps to Resolve Dependencies

1. **Declaring Dependencies**: In your project file (e.g., `.csproj`), you specify the packages that your project depends on. These are often high-level dependencies.
    
2. **Dependency Graph**: Each of these packages can have their own dependencies, which leads to a dependency graph. The graph includes both direct dependencies (specified in your project) and transitive dependencies (dependencies of your dependencies).
    
3. **Version Constraints**: Packages often specify version constraints for their dependencies. For example, a package might require a specific version range of another package.
    
4. **Conflict Resolution**: The dependency resolver must handle conflicts where different packages require different versions of the same dependency. It resolves these conflicts based on rules, such as preferring the highest compatible version.
    
5. **Restoring Packages**: Once the dependency graph is resolved and conflicts are handled, the `dotnet restore` command downloads all the required packages and their dependencies.
    
6. **Lock File**: The resolved dependencies are recorded in a lock file (`project.assets.json`). This file ensures that subsequent builds use the same versions of dependencies, providing consistency.
### Example of Dependency Resolution

Consider the following example:

- Your project depends on PackageA v1.0 and PackageB v2.0.
- PackageA v1.0 depends on PackageC >=1.0 <2.0.
- PackageB v2.0 depends on PackageC >=1.5 <3.0.

The dependency resolver will determine that the compatible version of PackageC that satisfies both constraints is v1.5.x.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
