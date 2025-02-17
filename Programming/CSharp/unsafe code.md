---
date_added: 2025-02-17
tags:
  - csharp
---
Up: [unsafe](unsafe.md)
___
 Most of the C# code you write is "verifiably safe code." _Verifiably safe code_ means .NET tools can verify that the code is safe. In general, safe code doesn't directly access memory using pointers. It also doesn't allocate raw memory. It creates managed objects instead.
 Unsafe code has the following properties:

- Methods, types, and code blocks can be defined as unsafe.
- In some cases, unsafe code can increase an application's performance by removing array bounds checks.
- Unsafe code is required when you call native functions that require pointers.
- Using unsafe code introduces security and stability risks.
- The code that contains unsafe blocks must be compiled with the [**AllowUnsafeBlocks**](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/compiler-options/language#allowunsafeblocks) compiler option. 
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
