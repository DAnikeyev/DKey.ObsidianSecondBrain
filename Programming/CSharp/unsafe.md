---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Modifiers](Modifiers.md)
___
 The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.
 ```cs
 unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}

//or

unsafe
{
    // Unsafe context: can use pointers here.
}


```
To compile unsafe code, you must specify the [**AllowUnsafeBlocks**](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/compiler-options/language#allowunsafeblocks) compiler option. Unsafe code is not verifiable by the common language runtime.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
