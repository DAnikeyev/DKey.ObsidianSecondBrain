---
date_added: 2025-02-19
tags: []
---
Up: [Declaration Statement](Declaration%20Statement.md)
___
 Is a type defined within a [Class](Class.md), [Struct](Struct.md) or [Interface](Interface.md)

```cs
public class Container
{
    class Nested
    {
        Nested() { }
    }
}
```
 Nested type can have [Access modifiers](Access%20modifiers.md) but can't be [[protected]] if it's inside of [[sealed]] class
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
