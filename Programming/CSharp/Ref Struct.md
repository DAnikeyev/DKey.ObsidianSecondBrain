---
date_added: 2025-01-20
tags:
  - csharp
---
Up: [Struct](Struct.md)
___
 ref modifier can be used to declare a struct that is not copied when passed as a parameter to a method. 
For example [[Span]] and [[ReadOnlySpan]] are structs that use the ref modifier 

## Restrictions
To ensure that Intances can't escape [Memory stack](Memory%20stack.md) compiler limits ref struct usage
- Ref struct can't be the element of array
- Can't be a type or a field of a class or a non-ref struct
- Can't be boxed
- Can't be used in methods in the same block with [[Await]]
- Can't be captured in [[Lambda Expressions]] or [[Local Functions]]
- Can't be used in iterators with [[Yield]] keyword
- Can't be a type argument unless ==allows ref struct== constraint is used
- 


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
