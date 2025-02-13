---
date_added: 2025-02-14
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___
 In the context of .NET, a **workload** is a modular package that extends the .NET SDK to support specific types of application development or target specific platforms.
### Examples
- **`maui`**: For building cross-platform mobile and desktop apps using .NET MAUI.
- **`android`**: For building Android applications.
- **`ios`**: For building iOS applications.
- **`web`**: For building web applications, which might include Blazor.
## commands
- `dotnet workload` - Provides information about the available workload commands and installed workloads.
- `dotnet workload sets` - Lists available workload sets.
- `dotnet workload install` - Installs a workload.
- `dotnet workload list` - Lists available workloads.
- `dotnet workload search` - Searches for workloads.
- `dotnet workload uninstall` - Uninstalls a workload.
- `dotnet workload update` - Updates a workload.
- `dotnet workload repair` - Repairs a workload.
- `dotnet workload config` - Configures workload settings.
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
