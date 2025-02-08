---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Compilation process](Compilation%20process.md)
___
 - **Compiler Platform**: Roslyn is a complete rewrite of the C# and VB.NET compilers in managed code. It is not just a compiler but a compiler platform that provides rich code analysis APIs.
    
- **Open Source**: Roslyn is open source and part of the .NET Foundation. It allows developers to build tools and applications that can analyze, modify, and generate C# and VB.NET code.
    
- **Integrated into .NET SDK**: Roslyn is integrated into the .NET SDK and is the default compiler for .NET Core and .NET 5+ projects. It provides the `csc.exe` functionality but with additional capabilities.
    
- **IDE Support**: Roslyn powers many of the features in Visual Studio and other IDEs, such as IntelliSense, refactoring, and code fixes. It provides real-time code analysis and feedback as you type.
    
- **Extensibility**: Because Roslyn exposes APIs for code analysis and transformation, developers can create custom analyzers and code fixes that integrate with the build process and development environment.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
