---
date_added: 2025-02-07
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___
 The `dotnet build` command builds the project and its dependencies into a set of binaries. The binaries include the project's code in Intermediate Language (IL) files with a _.dll_ extension. For executable projects targeting .NET Core 3.0 and later, library dependencies are copied to the output folder.
 
 ```cs
 dotnet build [<PROJECT>|<SOLUTION>] [-a|--arch <ARCHITECTURE>]
    [--artifacts-path <ARTIFACTS_DIR>]
    [-c|--configuration <CONFIGURATION>] [-f|--framework <FRAMEWORK>]
    [--disable-build-servers]
    [--force] [--interactive] [--no-dependencies] [--no-incremental]
    [--no-restore] [--nologo] [--no-self-contained] [--os <OS>]
    [-o|--output <OUTPUT_DIRECTORY>]
    [-p|--property:<PROPERTYNAME>=<VALUE>]
    [-r|--runtime <RUNTIME_IDENTIFIER>]
    [--self-contained [true|false]] [--source <SOURCE>]
    [--tl:[auto|on|off]] [--use-current-runtime, --ucr [true|false]]
    [-v|--verbosity <LEVEL>] [--version-suffix <VERSION_SUFFIX>]

dotnet build -h|--help
```

# Example :
```cs
dotnet build MyProject.csproj -c Release -f net7.0 --arch x64 -o ./buildOutput
```

## Steps of [Compilation process](Compilation%20process.md)
1. ︎• Discovery of the Solution File:  
    • The CLI first detects that you’re in a folder with a .sln file. If you simply run dotnet build without specifying a project file, it will assume you want to build the solution.  
    • The solution file acts as an aggregator that references all the individual project files.
    
2. ︎• Parsing the Solution File:  
    • The .sln file is parsed. This file defines the list of projects included in the solution, along with their relative paths.  
    • The order of projects or dependencies among them may be inferred from this file, which is later used to determine the build order.
    
3. ︎• Project Dependency Resolution:  
    • Each project (.csproj) file is examined to discover its dependencies on other projects, NuGet packages, or shared libraries.  
    • Dotnet build determines the correct build order based on these dependencies so that projects which are depended upon are built first.
    
4. ︎• Configuration and Environment Setup:  
    • The CLI reads configuration files such as global.json (if present), and nuget.config.  
    • It picks up runtime, SDK version, and other global settings which may affect the build process.
    
5. ︎• Restoring Dependencies:  
    • Although dotnet build can trigger a restore if needed, it ensures that all NuGet package dependencies are resolved (this is implicitly done unless you run with the --no-restore flag).  
    • Restored packages are downloaded from remote feeds if they are not already present in the local NuGet cache.
    
6. ︎• Loading Individual Projects:  
    • For each project referenced in the solution, the CLI reads the .csproj file to understand compilation options, target frameworks, output settings, compile items, resource files, and so on. • Any custom MSBuild targets or properties defined in the project file are processed.
    
7. ︎• Compilation Phase:  
    • MSBuild is invoked to compile the source code files in each project.  
    • The compiler translates the C# code into intermediate language (IL), performing optimizations and generating assembly files (DLLs or EXEs). • During compilation, several tasks are executed, like code analysis, generation of assembly information, and resource embedding.
    
8. ︎• Linking & Generating Outputs:  
    • After successful compilation, the built assemblies along with any required dependencies (PDB files for debugging, XML documentation) are placed in the respective output directories (typically bin/\<configuration>/\<framework>/). • If there are post-build events or custom build tasks defined in the .csproj files, they are executed at this point.
    
9. ︎• Building the Entire Dependency Graph:  
    • The entire process happens in the order determined by the dependency resolution step. This means that if one project relies on another (for example, a shared library), the shared library is built first.  
    • Incremental builds may be performed; in many cases, only projects with changes are recompiled.
    
10. ︎• Final Status and Reporting:  
    • The CLI collects build outputs, handles any warnings and errors, and summarizes the build result in the console output.  
    • If any errors occur, the build process is halted and error messages are provided to help diagnose the issue.


# Flags:
1. -a|--arch \<ARCHITECTURE> • Specifies the target processor architecture (e.g., x86, x64, arm).  
    Example:  
    dotnet build MyProject.csproj --arch x64
    
2. --artifacts-path \<ARTIFACTS_DIR> • Directory in which to place built output (e.g., logs, binaries) but is typically used in combination with specialized build workflows.
    
3. -c|--configuration \<CONFIGURATION> • Specifies the build configuration (e.g., Debug or Release). Default is Debug. Example:  
    dotnet build MyProject.csproj -c Release
    
4. -f|--framework \<FRAMEWORK> • Builds the project for a specific target framework (e.g., net7.0, net6.0). Example: dotnet build MyProject.csproj -f net7.0
    
5. --disable-build-servers • Disables the build servers (like the MSBuild server or VBCSCompiler) and forces a clean, isolated build.
    
6. --force • Forces all dependencies to be resolved again and re-downloaded (often combined with restore).
    
7. --interactive • Allows the command to prompt for user input or authentication (helpful in environments needing sign-in for private feeds).
    
8. --no-dependencies • Builds only the root project; does not traverse and build referenced projects.
    
9. --no-incremental • Performs a clean rebuild (forces MSBuild to ignore previously cached build inputs).
    
10. --no-restore • Skips calling “dotnet restore” before building. Useful if you have already restored or want to build offline.
    
11. --nologo • Hides the Microsoft build engine logo.
    
12. --no-self-contained • Builds an app that uses the machine’s globally installed runtime (instead of bundling the runtime). Equivalent to specifying --self-contained false.
    
13. --os \<OS> • Used with --arch to specify cross-compilation targeting a different OS (e.g., linux, win, osx).
    
14. -o|--output \<OUTPUT_DIRECTORY> • Specifies the output directory for the compiled assembly. Example: dotnet build MyProject.csproj -o ./buildOutput
    
15. -p|--property:\<PROPERTYNAME>=\<VALUE> • Sets an MSBuild property by name and value. You can pass multiple -p flags if needed. Example: dotnet build MyProject.csproj -p:DefineConstants=DEBUG;TRACE
    
16. -r|--runtime <RUNTIME_IDENTIFIER> • Builds the project for a specific [RID (Runtime Identifier)](RID%20(Runtime%20Identifier).md)], such as win10-x64, linux-arm, etc.
    
17. --self-contained \true|false • Controls whether the app is self-contained (bundles its own .NET runtime) or framework-dependent. See [self-contained app](self-contained%20app.md)
    
18. --source <SOURCE> • Adds an additional NuGet source (feed) to look for packages during restore/build.
    
19. --tl: auto|on|off • Enables, disables, or sets auto telemetrics logging for the command (rarely used in typical builds).
    
20. --use-current-runtime, --ucr true|false • Toggles whether the build should use the current runtime version on the machine.
    
21. -v|--verbosity \<LEVEL> • Sets the verbosity level of the build output (quiet, minimal, normal, detailed, diagnostic). Example: dotnet build MyProject.csproj -v detailed
    
22. --version-suffix \<VERSION_SUFFIX> • Appends a specified version suffix to the assembly’s version number (often used in CI/CD scenarios).
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
