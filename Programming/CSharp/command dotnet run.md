---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___
 Runs source code without any explicit compile or launch commands.
```cs
dotnet run [-a|--arch <ARCHITECTURE>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive]
    [--launch-profile <NAME>] [--no-build]
    [--no-dependencies] [--no-launch-profile] [--no-restore]
    [--os <OS>] [--project <PATH>] [-r|--runtime <RUNTIME_IDENTIFIER>]
    [--tl:[auto|on|off]] [-v|--verbosity <LEVEL>]
    [[--] [application arguments]]

dotnet run -h|--help
```

The `dotnet run` command is used in the context of projects, not built assemblies.

| Command            | Description                                                                                                                                              | Typical Use Case                                                                                                                                            |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **dotnet build**   | Compiles the source code and generates intermediate binaries (DLLs or EXEs). It checks for errors but does not execute the application.                  | Use during development to verify that the code compiles correctly without running the application, ideal for quick builds and error checking.               |
| **dotnet run**     | Builds the project (if necessary) and then executes the application in one step, combining compilation and runtime execution.                            | Ideal for local testing, debugging, and quick iterations during the development cycle when you want to compile and immediately run the application.         |
| **dotnet publish** | Prepares the application for deployment by compiling the code, including all necessary dependencies, and performing optimizations for a packaged output. | Best used when deploying your application (e.g., to production environments), ensuring that the final package contains all components needed for execution. |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
