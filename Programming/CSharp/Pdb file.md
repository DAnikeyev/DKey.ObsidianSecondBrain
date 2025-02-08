---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Compilation process](Compilation%20process.md)
___
Program DataBase file Is usually built in debug mode. or can be used  by [command dotnet build](command%20dotnet%20build.md). It contains:
- Mappings from the compiled binary’s instructions (or IL code in .NET) to the corresponding lines of source code.
- Symbol information such as function names, local variables, and data types.
- Metadata that helps the debugger step through the code accurately, inspect variable values, and show the call stack.
- References to the source file paths so that the debugger can load the correct files during a debugging session.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
