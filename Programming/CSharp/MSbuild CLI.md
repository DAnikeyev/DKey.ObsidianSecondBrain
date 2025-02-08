---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Compilation process](Compilation%20process.md)
___

is usually called by [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md) during [command dotnet build](command%20dotnet%20build.md), [command dotnet publish](command%20dotnet%20publish.md) or [command dotnet run](command%20dotnet%20run.md).

By default MSBuild uses [Roslyn compiler](Roslyn%20compiler.md), but custom compiler can be specified 
```cs
msbuild MyProject.csproj /p:CscToolPath=path\to\custom\compiler /p:CscToolExe=csc.exe
```
### Syntax

`MSBuild.exe [Switches] [ProjectFile]`

Here are some common MSBuild command-line switches:

1. **`/target` or `/t`**: Specifies the target(s) to build. For example, `/t:Clean;Build` will clean and then build the project.
    
2. **`/property` or `/p`**: Sets or overrides project properties. For example, `/p:Configuration=Release` sets the build configuration to Release.
    
3. **`/verbosity` or `/v`**: Specifies the amount of information to display in the build output. Options include `quiet`, `minimal`, `normal`, `detailed`, and `diagnostic`.
    
4. **`/fileLogger` or `/fl`**: Enables logging to a file. You can specify additional parameters like the log file name.
    
5. **`/logger`**: Specifies a logger to use for the build output. You can use custom loggers by specifying their assembly and class.
    
6. **`/maxcpucount` or `/m`**: Specifies the maximum number of concurrent processes to use when building. This can speed up the build process on multi-core machines.
    
7. **`/nologo`**: Suppresses the display of the startup banner and copyright message.
    
8. **`/help` or `/?`**: Displays help information about MSBuild command-line options.
    
9. **`/restore`**: Restores the project dependencies and tools before building.
    
10. **`/noincremental`**: Forces a clean build, ignoring any previously built outputs.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
