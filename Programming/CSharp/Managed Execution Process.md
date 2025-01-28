---
date_added: 2025-01-29
tags:
  - csharp
---
Up: [[CLR]]
___

1. Choosing a compiler and a target runtime.
2. Compiling code into [Intermediate Language](Intermediate%20Language.md)
3. Compiling [Intermediate Language](Intermediate%20Language.md) code into [[Native code]] using [JIT](JIT.md) During this compilation, code must pass a verification process that examines the CIL and metadata to find out whether the code can be determined to be type safe
4. Running code, using infrustructure of [[CLR]]
### Choosing a compiler(s)

To obtain the benefits provided by the common language runtime (CLR), you must use one or more language compilers that target the runtime, such as Visual Basic, C#, Visual C++, F#, or one of many third-party compilers such as an Eiffel, Perl, or COBOL compiler.
If your component must be completely usable by components written in other languages, your component's exported types must expose only language features that are included in the [[CLS]]

### Compiling
Because the common language runtime supplies one or more JIT compilers for each computer architecture it supports, the same set of CIL can be JIT-compiled and run on any supported architecture.
As alternative The Native Image Generator (Ngen.exe) is a tool that improves the performance of managed applications. Ngen.exe creates native images

### Code Verification
The runtime relies on the fact that the following statements are true for code that is verifiably type safe:

- A reference to a type is strictly compatible with the type being referenced.
- Only appropriately defined operations are invoked on an object.
- Identities are what they claim to be.

This can be bypassed, for example by editing `machine.config` settings 

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
