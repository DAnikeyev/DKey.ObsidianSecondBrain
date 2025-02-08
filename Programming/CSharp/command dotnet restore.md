---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___
 Restores the dependencies and tools of a project. 

## Implicit restore
is run by commands
 - [command dotnet new](command%20dotnet%20new.md)
 - [command dotnet build](command%20dotnet%20build.md)
 - [command dotnet build-server](command%20dotnet%20build-server.md)
 - [command dotnet run](command%20dotnet%20run.md)
 - [command dotnet publish](command%20dotnet%20publish.md)
 - [command dotnet pack](command%20dotnet%20pack.md)
 - [command dotnet test](command%20dotnet%20test.md)

Sometimes, it might be inconvenient to run the implicit NuGet restore with these commands. For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage. To prevent the implicit NuGet restore, you can use the `--no-restore` flag with any of these commands.

## Dependencies location
Downloaded references are stored in local cache. `%userprofile%\.nuget\packages` for WINDOWS and `~/.nuget/packages` for UNIX systems.
o restore the dependencies, NuGet needs the feeds where the packages are located. Feeds are usually provided via the _nuget.config_ configuration file. A default configuration file is provided when the .NET SDK is installed.
- Create your own _[[nuget.config]]_ file in the project directory. For more information, see [Common NuGet configurations](https://learn.microsoft.com/en-us/nuget/consume-packages/configuring-nuget-behavior) and [nuget.config differences](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-restore#nugetconfig-differences). For example, setting the `globalPackagesFolder` in _nuget.config_ places the restored NuGet packages in the specified folder. 
- Use [command dotnet nuget](command%20dotnet%20nuget.md) commands such as [`dotnet nuget add source`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-nuget-add-source).
## Arguments
- **`ROOT`**
    Optional path to the project file to restore.

## Options
- **`-h|--help`**
    Show command line help.
  - -r|--runtime <RUNTIME_IDENTIFIER>
    Specifies the target [RID (Runtime Identifier)](RID%20(Runtime%20Identifier).md) to restore packages for. For example, win-x64, linux-x64.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
