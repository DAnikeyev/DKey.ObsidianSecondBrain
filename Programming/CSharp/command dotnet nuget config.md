---
date_added: 2025-02-14
tags:
  - csharp
---
Up: [command dotnet nuget](command%20dotnet%20nuget.md)
___
## dotnet nuget config get
Gets the NuGet configuration settings that will be applied.
```cs
dotnet nuget config get <ALL | CONFIG_KEY> [--show-path] [--working-directory <DIRECTORY>]

dotnet nuget config get -h|--help
```
## dotnet nuget config set
Set the value of a specified NuGet configuration setting.
```cs
dotnet nuget config set <CONFIG-KEY> <CONFIG-VALUE> [--configfile <FILE>]

dotnet nuget config set -h|--help
```
## dotnet nuget config unset
Removes the key-value pair from a specified NuGet configuration setting.
```cs
dotnet nuget config unset <CONFIG-KEY> [--configfile <FILE>]

dotnet nuget config unset -h|--help
```
## dotnet nuget config paths
Lists nuget configuration files currently being applied to a directory.
```cs
dotnet nuget config paths [--working-directory <DIRECTORY>]

dotnet nuget config paths -h|--help
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
