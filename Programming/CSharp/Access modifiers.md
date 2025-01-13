---
date_added: 2025-01-13
tags: []
---
Up: [Assembly](Assembly.md)
___
- [public](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/public): Code in any assembly can access this type or member. The accessibility level of the containing type controls the accessibility level of public members of the type.
- [private](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/private): Only code declared in the same `class` or `struct` can access this member.
- [protected](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/protected): Only code in the same `class` or in a derived `class` can access this type or member.
- [internal](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/internal): Only code in the same assembly can access this type or member.
- [protected internal](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/protected-internal): Only code in the same assembly _or_ in a derived class in another assembly can access this type or member.
- [private protected](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/private-protected): Only code in the same assembly _and_ in the same class or a derived class can access the type or member.
- [file](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/file): Only code in the same file can access the type or member.

InternalsAreVisibleTo attribute can be used to make internal members visible to other assemblies for testing purposes.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
