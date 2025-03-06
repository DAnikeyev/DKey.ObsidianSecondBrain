---
date_added: 2025-02-02
tags:
  - csharp
---
Up: [[Reflection]]
___
 Used to discover [Method](Method.md) information such as the name, return type, parameters, access modifiers, and implementation details. Use the [GetMethods](https://learn.microsoft.com/en-us/dotnet/api/system.type.getmethods) or [GetMethod](https://learn.microsoft.com/en-us/dotnet/api/system.type.getmethod) method of [[Type]] to invoke a specific method.

>[!Info]
> MethodInfo.Invoke can be used to invoke a method with parameters and return a value. However, it is slower than a direct call to the method. or using a delegate


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
