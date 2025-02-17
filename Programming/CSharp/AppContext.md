---
date_added: 2025-02-17
tags:
  - csharp
---
Up: [Application environment](Application%20environment.md)
___

| Property                                                                                                                                                     |                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| [BaseDirectory](https://learn.microsoft.com/en-us/dotnet/api/system.appcontext.basedirectory?view=net-9.0#system-appcontext-basedirectory)                   | Gets the file path of the base directory that the assembly resolver uses to probe for assemblies. |
| [TargetFrameworkName](https://learn.microsoft.com/en-us/dotnet/api/system.appcontext.targetframeworkname?view=net-9.0#system-appcontext-targetframeworkname) | Gets the name of the framework version targeted by the current application.                       |

| Method                                                                                                                                                                                    |                                                                                         |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| [GetData(String)](https://learn.microsoft.com/en-us/dotnet/api/system.appcontext.getdata?view=net-9.0#system-appcontext-getdata\(system-string\))                                         | Returns the value of the named data element assigned to the current application domain. |
| [SetData(String, Object)](https://learn.microsoft.com/en-us/dotnet/api/system.appcontext.setdata?view=net-9.0#system-appcontext-setdata\(system-string-system-object\))                   | Sets the value of the named data element assigned to the current application domain.    |
| [SetSwitch(String, Boolean)](https://learn.microsoft.com/en-us/dotnet/api/system.appcontext.setswitch?view=net-9.0#system-appcontext-setswitch\(system-string-system-boolean\))           | Sets the value of a switch.                                                             |
| [TryGetSwitch(String, Boolean)](https://learn.microsoft.com/en-us/dotnet/api/system.appcontext.trygetswitch?view=net-9.0#system-appcontext-trygetswitch\(system-string-system-boolean@\)) |                                                                                         |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
