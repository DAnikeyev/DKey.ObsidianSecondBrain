---
date_added: 2025-02-07
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___

## Helpers
 ```csharp
 dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
 ```

## Run a command
```csharp
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

## Run an application
``` csharp
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--depsfile <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    [--runtimeconfig <PATH>]
    <PATH_TO_APPLICATION> [arguments]
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
