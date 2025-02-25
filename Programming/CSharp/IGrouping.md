---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Collection Interface](Collection%20Interface.md)
___
 Represents a collection of objects that have a common key.
 ```
IGrouping<System.Reflection.MemberTypes, System.Reflection.MemberInfo> group =
    typeof(String).GetMembers().
    GroupBy(member => member.MemberType).
    First();
```

For example [Enumerable.GroupBy](Enumerable.GroupBy.md) or [Enumerable.ToLookup](Enumerable.ToLookup.md) returns a collection of IGrouping objects.
 
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
