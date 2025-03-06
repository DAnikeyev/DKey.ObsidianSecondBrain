---
date_added: 2025-03-06
tags:
  - csharp
---
Up: [Common attributes](Common%20attributes.md)
___
Can be used for conditionally preserving attribute in metadata based on configuration.
 ```csharp
 //#define TEST
#define VERIFY
using System;
using System.Diagnostics;
[Conditional("TEST")][Conditional("VERIFY")]
public sealed class CondAttribute : Attribute 
{
}
	
[Cond]
public sealed class Program {
public static void Main() {
Console.WriteLine("CondAttribute is {0}applied to Program type.",
Attribute.IsDefined(typeof(Program),
typeof(CondAttribute)) ? "" : "not ");
}
}
 ```
 
>[!Info]
>  Conditional compilation symbols field in IDE can be specified in build configuration to set different values for debug/release.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
