---
date_added: 2025-03-03
tags:
  - csharp
---
Up: [Exception](Exception.md)
___
 Are attributes of System.CompilerServices namespace that provide information about the caller to the callee
 ```cs
 public void Log([CallerLineNumber] int line = -1,
[CallerFilePath] string path = null,
[CallerMemberName] string name = null)
{
Console.WriteLine((line < 0) ? "No line" : "Line " + line);
Console.WriteLine((path == null) ? "No file path" : path);
Console.WriteLine((name == null) ? "No member name" : name);
Console.WriteLine();
}

//output
Line 12
c:\ProCSharp\ErrorsAndExceptions\CallerInformation\Program.cs
Main
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
