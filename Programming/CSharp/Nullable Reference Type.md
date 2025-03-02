---
date_added: 2025-01-22
tags:
  - csharp
---
Up: [CTS](CTS.md)
___
 Is a group of features that helps to verify that code causes runtime to throw `System.NullReferenceException`

**Enabling NRT**: Nullable reference types are an opt-in feature. You can enable them in your project by setting `<Nullable>enable</Nullable>` in your project file or by using `#nullable enable` in your code files.

At runtime, nullable reference types behave the same as regular reference types. The nullability annotations do not affect the runtime behavior of your code.

Compiler tracks null-state of every expression and determine the nullability of it and the assign target variables as 
- _not-null_: The expression (variable) is known to be not-`null`.
- _maybe-null_: The expression (variable) might be `null`.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
