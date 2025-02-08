---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___
 The `dotnet build-server` command is used to manage the .NET build servers that are responsible for improving the performance of build operations. These build servers include the CoreCLR JIT compiler server (`VBCSCompiler`), the Razor compilation server, and others that can be used to speed up builds by caching and reusing resources.
 ```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown -h|--help
dotnet build-server -h|--help
dotnet build-server start
```

###  Key Build Servers

1. **CoreCLR JIT Compiler Server (`VBCSCompiler`)**:
    - This server is used by the Roslyn compiler to improve the performance of C# and VB.NET compilations.
    - It caches compilation results and keeps the compiler process running to avoid the overhead of starting a new process for each build.
2. **Razor Compilation Server**:
    - Used in ASP.NET Core projects to compile Razor views and pages.
    - It speeds up the build process by caching compiled Razor files.
3. **Other Potential Servers**:
    - Depending on the .NET SDK and tools you are using, there might be additional build servers for specific tasks or optimizations.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
