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

## Rules


#### Lowest applicable version

The lowest applicable version rule restores the lowest possible version of a package as defined by its dependencies.


#### Floating versions

A floating dependency version is specified with the * character. For example, `6.0.*`. This version specification says "use the latest 6.0.x version"; `4.*` means "use the latest 4.x version."


#### Direct dependency wins

When the package graph for an application contains different versions of a package in the same subgraph, and one of those versions is a direct dependency in that subgraph, that version would be chosen for that subgraph and the rest will be ignored. This behavior allows an application to override any particular package version in the dependency graph.

>[!Warning]
> The Direct dependency wins rule can result in a downgrade of the package version, thus potentially breaking other dependencies in the graph. When a package is downgraded, NuGet adds a [warning to alert the user](https://learn.microsoft.com/en-us/nuget/reference/errors-and-warnings/nu1605).


### Cousin dependencies

When different package versions are referred in different subgraphs in the graph from the application, NuGet uses the lowest version that satisfies all version requirements

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
