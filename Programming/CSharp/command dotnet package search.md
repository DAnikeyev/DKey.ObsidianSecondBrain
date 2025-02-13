---
date_added: 2025-02-14
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___
 Searches for a NuGet package. 
 ```cs
 dotnet package search <SEARCH TERM> [--configfile <FILE>] [--exact-match] [--format <FORMAT OPTION>]
    [--interactive] [--prerelease] [--skip <NUMBER>] [--source <SOURCE>] [--take <NUMBER>]
    [--verbosity <VERBOSITY VALUE>]

dotnet package search -h|--help
```

## Example
```cs
dotnet package search Newtonsoft.Json --source https://api.nuget.org/v3/index.json --format json
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
