---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)]
___
`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.
The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution. It's the only officially supported way to prepare the application for deployment. Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET shared runtime installed on it.

```cs
dotnet publish [<PROJECT>|<SOLUTION>] [-a|--arch <ARCHITECTURE>]
    [--artifacts-path <ARTIFACTS_DIR>]
    [-c|--configuration <CONFIGURATION>] [--disable-build-servers]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive]
    [--manifest <PATH_TO_MANIFEST_FILE>] [--no-build] [--no-dependencies]
    [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [--os <OS>] [-r|--runtime <RUNTIME_IDENTIFIER>]
    [--sc|--self-contained [true|false]] [--no-self-contained]
    [-s|--source <SOURCE>] [--tl:[auto|on|off]]
    [--use-current-runtime, --ucr [true|false]]
    [-v|--verbosity <LEVEL>] [--version-suffix <VERSION_SUFFIX>]

dotnet publish -h|--help
```

# Main flags:
- `-o|--output <OUTPUT_DIRECTORY>`: Specifies the output directory for the published output. Like `bin/Release/net5.0/publish`.
- `-c|--configuration <CONFIGURATION>`: Specifies the configuration to build. Like  `Debug`, `Release`, etc.
- `-f|--framework <FRAMEWORK>`: Specifies the target framework to build for. Like `net5.0`, `net6.0`, etc.
- `--self-contained [true|false]`: Publishes the .NET runtime with the application. If `true`, the output will be a self-contained deployment. If `false`, the output will be a framework-dependent deployment.
- `-r|--runtime <RUNTIME_IDENTIFIER>`: Specifies the target runtime to publish for. Like `win-x64`, `linux-x64`, etc.
- `--no-build`: Skips building the project before publishing. Useful when you want to publish without building the project again.
- ``--artifacts-path <ARTIFACTS_DIR>``: Specifies the directory where build artifacts are placed. Useful for incremental builds.
- `--no-restore`: Skips the implicit restore step before publishing. Useful when you want to publish without restoring the project's dependencies.
- `--os <OS>`: Specifies the target operating system to publish for. Like `windows`, `linux`, etc.
- ``--version-suffix <VERSION_SUFFIX>``: Defines the version suffix to append to the published output folder name. Useful for differentiating between different versions of the same application. like `beta`, `rc`, etc.

## Additional Files in a Publish Output

Below are common examples of files that are present in a publish output but not in a standard build output:

| File Name                     | Description                                                                                                                                 |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| MyApp.runtimeconfig.json      | Contains runtime configuration settings for the .NET runtime, ensuring that the correct version and options are used.                       |
| MyApp.deps.json               | Provides detailed dependency information, mapping out all libraries your application requires at runtime.                                   |
| web.config                    | (For ASP.NET Core apps) Configures the application when hosted in environments like IIS.                                                    |
| Additional Static Assets      | Static files such as HTML, CSS, JavaScript, images, and other content files marked as "Content" in your project.                            |
| Platform-Specific Executables | When publishing as a self-contained deployment, an executable specific to the target platform (e.g., MyApp.exe on Windows) may be produced. |

## Summary

- The **build output** (via `dotnet build`) primarily focuses on compiling code and generating the necessary binaries.
- The **publish output** (via `dotnet publish`) is geared towards deployment and includes extra files such as runtime configuration, dependency mapping, hosting configurations, and any additional static content required by the application.

This differentiation ensures that your deployed application has everything it needs to run reliably in its target environment.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
