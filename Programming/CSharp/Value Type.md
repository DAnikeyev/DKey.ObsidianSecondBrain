---
date_added: 2024-10-08
tags:
  - csharp
  - dotnet
sr-due: 2025-04-09
sr-interval: 15
sr-ease: 290
---
Up: [[CTS]]
___
Contains the actual data. by default on assignment, passing argument to a method, or returning from a method, a copy of the value is made. If Value type contains a reference type, the reference is copied, but the object is not. Value types are stored on the [Memory stack](Memory%20stack.md) unless 
 - they are fields of [Reference Type](Reference%20Type.md) 
 - [Boxing and Unboxing](Boxing%20and%20Unboxing.md) is used.
 - They are inside [async](async.md) method (state machine is stored on the heap)
 - They are inside [Iterator](Iterator.md) method (state machine is stored on the heap)

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
 1. [Reference Type](Reference%20Type.md)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
