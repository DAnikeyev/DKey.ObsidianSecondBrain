---
date_added: 2024-10-08
tags:
  - csharp
  - dotnet
---
Up: [Object](Object.md)
___
Contains the actual data. by default on assignment, passing argument to a method, or returning from a method, a copy of the value is made. If Value type contains a reference type, the reference is copied, but the object is not. Value types are stored on the [Memory stack](Memory%20stack.md).

## Value types
- [[Struct]]
- [[Enumeration type]]

## Build-in value types aka Simple types:
- [[bool]]
- [[Intergral numeric type]]
- [[char]]
- [[Floating-point numeric type]]

> [!Info] 
Simple types can be declared using literals, like 42, 'c', or true.
You can declare constants of simple types using the const keyword.

Constant expressions are evaluated at compile time.


>[!Note] To make your code less error-prone and more robust, define and use [[Immutable]] value types.
>


# References
 1. [Value Type](Value%20Type.md)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
