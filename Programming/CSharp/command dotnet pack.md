---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___
 `dotnet pack` - Packs the code into a NuGet package.
```cs
dotnet pack [<PROJECT>|<SOLUTION>] [--artifacts-path <ARTIFACTS_DIR>]
    [-c|--configuration <CONFIGURATION>] [--force]
    [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output <OUTPUT_DIRECTORY>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--serviceable] [--tl:[auto|on|off]] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet pack -h|--help
```
The result of this command is a NuGet package (that is, a _.nupkg_ file).
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
