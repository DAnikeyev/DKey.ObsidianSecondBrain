---
date_added: 2025-02-14
tags:
  - csharp
---
Up: [Nuget package](Nuget%20package.md)
___
Constraints are stored in [csproj file](csproj%20file.md) or packages.config file

Version follows [[SemVer2.0]] but has few modification:
1. `NuGetVersion` supports a 4th version segment, `Revision`, to be compatible with, or a superset of, [`System.Version`](https://learn.microsoft.com/en-us/dotnet/api/system.version). Therefore, excluding prerelease and metadata labels, a version string is `Major.Minor.Patch.Revision`. As per version normalization described above, if `Revision` is zero, it is omitted from the normalized version string.
2. `NuGetVersion` only requires the major segment to be defined. All others are optional, and are equivalent to zero. This means that `1`, `1.0`, `1.0.0`, and `1.0.0.0` are all accepted and equal.
3. `NuGetVersion` uses case insensitive string comparisons for pre-release components. This means that `1.0.0-alpha` and `1.0.0-Alpha` are equal.

Used for [Resolving nuget dependencies](Resolving%20nuget%20dependencies.md)

| Notation  | Applied rule  | Description                                           |
| --------- | ------------- | ----------------------------------------------------- |
| 1.0       | x ≥ 1.0       | Minimum version, inclusive                            |
| [1.0,)    | x ≥ 1.0       | Minimum version, inclusive                            |
| (1.0,)    | x > 1.0       | Minimum version, exclusive                            |
| [1.0]     | x == 1.0      | Exact version match                                   |
| (,1.0]    | x ≤ 1.0       | Maximum version, inclusive                            |
| (,1.0)    | x < 1.0       | Maximum version, exclusive                            |
| [1.0,2.0] | 1.0 ≤ x ≤ 2.0 | Exact range, inclusive                                |
| (1.0,2.0) | 1.0 < x < 2.0 | Exact range, exclusive                                |
| [1.0,2.0) | 1.0 ≤ x < 2.0 | Mixed inclusive minimum and exclusive maximum version |
| (1.0)     | invalid       | invalid                                               |

## Example
```xml
<!-- Accepts any version 6.1 and above.
     Will resolve to the smallest acceptable stable version.-->
<PackageReference Include="ExamplePackage" Version="6.1" />

<!-- Accepts any 6.x.y version.
     Will resolve to the highest acceptable stable version.-->
<PackageReference Include="ExamplePackage" Version="6.*" />

<!-- Accepts any version above, but not including 4.1.3. Could be
     used to guarantee a dependency with a specific bug fix. 
     Will resolve to the smallest acceptable stable version.-->
<PackageReference Include="ExamplePackage" Version="(4.1.3,)" />

<!-- Accepts any version up below 5.x, which might be used to prevent pulling in a later
     version of a dependency that changed its interface. However, this form is not
     recommended because it can be difficult to determine the lowest version. 
     Will resolve to the smallest acceptable stable version.
     -->
<PackageReference Include="ExamplePackage" Version="(,5.0)" />

<!-- Accepts any 1.x or 2.x version, but not 0.x or 3.x and higher.
     Will resolve to the smallest acceptable stable version.-->
<PackageReference Include="ExamplePackage" Version="[1,3)" />

<!-- Accepts 1.3.2 up to 1.4.x, but not 1.5 and higher.
     Will resolve to the smallest acceptable stable version. -->
<PackageReference Include="ExamplePackage" Version="[1.3.2,1.5)" />
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
