---
date_added: 2025-02-14
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___
### Install
```cs
dotnet tool install <PACKAGE_NAME> -g|--global
    [--allow-downgrade] [-a|--arch <ARCHITECTURE>]
    [--add-source <SOURCE>] [--configfile <FILE>] [--disable-parallel]
    [--framework <FRAMEWORK>] [--ignore-failed-sources] [--interactive]
    [--no-cache] [--prerelease]
    [--tool-manifest <PATH>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]
```

## List
 ```csharp
 dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list [<PACKAGE_ID>]

dotnet tool list

dotnet tool list -h|--help
 ```
## Restore
Installs the .NET local tools that are in scope for the current directory.
 ```csharp
 
 dotnet tool restore
    [--configfile <FILE>] [--add-source <SOURCE>]
    [--tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
 ```

# Run
```cs
dotnet tool run <COMMAND NAME>

dotnet tool run -h|--help
```

# Uninstall
```cs 
dotnet tool uninstall <PACKAGE_NAME> -g|--global

dotnet tool uninstall <PACKAGE_NAME> --tool-path <PATH> [--tool-manifest <PATH>]

dotnet tool uninstall <PACKAGE_NAME>

dotnet tool uninstall -h|--help
```

# Update

```cs
dotnet tool update <PACKAGE_ID> -g|--global
    [--add-source <SOURCE>] [--allow-downgrade]
    [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive]
    [--no-cache] [--prerelease]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]
```

## Search
```cs
dotnet tool search [--detail]  [--prerelease]
    [--skip <NUMBER>] [--take <NUMBER>] <SEARCH TERM>

dotnet tool search -h|--help
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
