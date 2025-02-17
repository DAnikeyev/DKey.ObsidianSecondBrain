---
date_added: 2025-02-17
tags:
  - csharp
---
Up: [Attribute](Attribute.md)
___
 Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.
 For example, the [AssemblyVersionAttribute](https://learn.microsoft.com/en-us/dotnet/api/system.reflection.assemblyversionattribute) attribute can be used to embed version information into an assembly, like this:

```cs
[assembly: AssemblyVersion("1.0.0.0")]
```
Global attributes appear in the source code after any top level `using` directives and before any type, module, or namespace declarations.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
