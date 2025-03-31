---
date_added: 2025-01-12
tags:
  - csharp
sr-due: 2025-03-29
sr-interval: 4
sr-ease: 274
---
Up: [CLR](CLR.md)
___
 Common type system (CTS) defines how typed are declared, used and managed in [CLR](CLR.md)
![](Pasted%20image%2020250113062220.png)
## Features
 - Framework for cross-language integration, type safety  and high performance code execution
 - Object-oriented programming model that supports the complete implementation of many programming languages
 - Defines rules that languages must follow, which helps ensure that objects written in different languages can interact with each other
 - Provide a library of base data types like Int32, Int64, and Boolean.
### Role of CTS in C#

- **Cross-Language Integration**: CTS allows objects written in different programming languages to interact with each other. This means that a class written in C# can be used in a Visual Basic .NET program, and vice versa.
- **Common Representation of Types**: CTS defines a set of data types that are used by all .NET languages. This ensures that the same data type in different languages have a consistent representation, which is crucial for interoperability.
- **Type Safety**: CTS enforces strict type rules at runtime, which helps in preventing type errors. This ensures that operations are performed on compatible types, enhancing the robustness of the application.
- **High-Performance Code Execution**: By providing a common type system, CTS allows the .NET runtime to optimize code execution for different types, resulting in better performance.

## Types in CTS
 - [[Class]]
 - [[Interface]]
 - [Delegate](Delegate.md)
 - [[Enumeration]]
 - [[Struct]]
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
