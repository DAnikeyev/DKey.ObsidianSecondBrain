---
date_added: 2025-02-18
tags:
  - csharp
---
Up: [[CLR]]
___
 Also known as VMT or V-table
 - The VMT is a table of function pointers that enables polymorphism in .NET
- It allows objects to determine at runtime which method implementation to call, especially for inherited and overridden methods
- Each class that contains or inherits virtual methods has its own VMT
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
