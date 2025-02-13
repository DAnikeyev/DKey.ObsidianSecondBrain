---
date_added: 2025-02-14
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___
 Restarts or [[hot reload]]s the specified application, or runs a specified dotnet command, when changes in source code are detected.
 ```cs
 dotnet watch [<command>]
  [--list]
  [--no-hot-reload] [--non-interactive]
  [--project <PROJECT>]
  [-q|--quiet] [-v|--verbose]
  [--version]
  [--] <forwarded arguments> 

dotnet watch -?|-h|--help
```

The `dotnet watch` command is a file watcher. When it detects a change, it runs the `dotnet run` command or a specified `dotnet` command. If it runs `dotnet run`, and the change is supported for [hot reload](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-watch#hot-reload), it hot reloads the specified application.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
