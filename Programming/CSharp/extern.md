---
date_added: 2025-02-20
tags:
  - csharp
---
Up: [Modifiers](Modifiers.md)
___
 The `extern` modifier is used to declare a method that is implemented externally. A common use of the `extern` modifier is with the `DllImport` attribute when you are using Interop services to call into unmanaged code [P-Invoke](P-Invoke.md).
```cs
[DllImport("avifil32.dll")]
private static extern void AVIFileInit();
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
