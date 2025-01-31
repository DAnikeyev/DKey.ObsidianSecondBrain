---
date_added: 2025-01-30
tags:
  - csharp
---
Up: [Delegate](Delegate.md) [Interface](Interface.md)
___
 Both types separate declaration from implementation.
 
 Use a delegate in the following circumstances:
- An eventing design pattern is used.
- It is desirable to encapsulate a static method.
- The caller has no need to access other properties, methods, or interfaces on the object implementing the method.
- Easy composition is desired.
- A class may need more than one implementation of the method.
    

Use an interface in the following circumstances:
- There is a group of related methods that may be called.
- A class only needs one implementation of the method.
- The class using the interface will want to cast that interface to other interface or class types.
- The method being implemented is linked to the type or identity of the class: for example, comparison methods.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
