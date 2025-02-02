---
date_added: 2024-10-08
tags:
  - dotnet
---
Up: [CLR](CLR.md)
___
refers to code or resources outside of [[CLR]], for example written on languages like C or C++.

Here are some key characteristics of unmanaged code:

1. **Direct Execution**: Unmanaged code is executed directly by the operating system, without the intervention of the CLR. This means it doesn't benefit from the services provided by the CLR, such as garbage collection, type safety, and exception handling.
    
2. **Memory Management**: In unmanaged code, developers are responsible for managing memory manually. This includes allocating and freeing memory, which can lead to issues like memory leaks or buffer overflows if not handled correctly.
    
3. **Platform-Specific**: Unmanaged code is often platform-specific, meaning it is compiled for a specific operating system and processor architecture. This contrasts with managed code, which is designed to be platform-independent and runs on any system with the appropriate version of the CLR.
    
4. **[[Interoperability]]**: [[Managed code]] (such as C# or VB.NET) can interact with unmanaged code through Platform Invocation Services (P/Invoke) or COM Interop. This allows .NET applications to use existing libraries and APIs written in unmanaged languages.
    
5. **Examples**: Common examples of unmanaged code include Windows API functions, legacy libraries written in C/C++, and certain performance-critical components that require direct hardware access.
## Content
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
