---
date_added: 2024-10-08
tags:
  - design
  - csharp
---
Up: [Design pattern](Design%20pattern.md)
___
You can always use new() keyword to create an [object](Object.md), but it's not always the best way to create an [object](Object.md). The creational design pattern provides a way to create objects while hiding the creation logic, rather than instantiating objects directly using new operator.
# Creating objects
- Invoke creation on [managed heap](Managed%20heap.md). [[Object]] doesn't need to be destroyed manually because [[Garbage Collector]] will take care of it.
- Stack allocation with [[Stackalloc]] allocates memory on the [[Memory stack ||stack]].  They will be cleaned up automatically when they go out of scope. This construct is used only with [[Value Type]].
- Allocation of [[Unmanaged memory |unmanaged]] memory with Marshal.AllocHGlobal or Marshal.AllocCoTaskMem. This memory must be released with Marshal.FreeHGlobal or Marshal.FreeCoTaskMem. This usually need for [[Interoperability|interoperation]] with unmanaged code.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
