---
date_added: 2025-01-13
tags:
  - csharp
---
Up: [Class](Class.md)
___
 A variable of any type that is defined inside a [[Class]] or a [[Struct]]
 - Field can be instance or [[static]]. Static fields are shared across all instances of a class. 
 - Field can be declared [[Readonly]]. Readonly fields can only be assigned a value during declaration or in the constructor of the class. 
 - Field can be declared [[Constant]]. Const fields are compile-time constants and their value cannot be changed. 
 - Field can be declared [[Volatile]]. Volatile fields are not subject to compiler optimizations that assume access by a single thread. 
 - Field can be declared [[Required]]. 

Generally you should declare private or protected fields and provide public [Property](Property), [Method](Method) or [CSharp Indexer](CSharp%20Indexer.md) to access them externally. 

Fields are initialized immediately before the constructor for the object instance is called
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
