---
date_added: 2025-02-20
tags:
  - csharp
---
Up: [Modifiers](Modifiers.md)
___
 The `abstract` modifier indicates that the thing being modified has a missing or incomplete implementation. The abstract modifier can be used with classes, methods, properties, indexers, and events.
Abstract methods have the following features:
- An abstract method is implicitly a virtual method.

- Abstract method declarations are only permitted in abstract classes.

- Because an abstract method declaration provides no actual implementation, there is no method body; the method declaration simply ends with a semicolon and there are no curly braces ({ }) following the signature. For example:
```cs
public abstract void MyMethod();
```
    
- It is an error to use the [[static]] or [virtual](virtual.md) modifiers in an abstract method declaration.
- Starting with C# 8.0, interfaces can define static members, and with C# 11, interfaces can define static abstract members.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
