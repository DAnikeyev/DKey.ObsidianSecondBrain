---
date_added: 2025-03-02
tags:
  - csharp
---
Up: [Class](Class.md)
___
 To use the partial keyword, simply place partial before class, struct, or interface.
 Nested partials are allowed as long as the partial keyword precedes the class keyword in the nested type.
Attributes, XML comments, interfaces, generic-type parameter attributes, and members are combined when
the partial types are compiled into the type.
>[!Info]
> Attributes combine!

Partial method is method that declared but defined in other file of that object type

>[!Info]
> If there’s not an implementation,the compiler removes the invocation of this method: A partial method needs to be of type void. Otherwise the compiler cannot remove the invocation in case no implementation exists.

>[!Warning]
>1. **Using Directive**: The `using ...Extensions;` directive is necessary to make the extension methods in that namespace available in your current file. In that case, type will have extension methods when loaded
> 
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
