---
date_added: 2025-01-24
tags: []
---
Up: [CTS](CTS.md)
___
 Common Language Specification is a list of rules and minimum features that a language must support to be able to interoperate with other .NET languages. It is a subset of the Common Type System (CTS) and defines rules that languages must follow, which helps ensure that objects written in different languages can interact with each other. 
 The text of the rules is taken verbatim from the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/)
Not following CLS make problems for [[Interoperablity]]. If an exposed type is unsupported by CLS not all languages can use it.

>[!Info]
> The rules for CLS compliance apply only to a component's public interface, not to its private implementation.

You can specify that a type or member is CLS-compliant by using the CLSCompliantAttribute attribute, or by setting 
```cs
[assembly:CLSCompliant(true)]
```
Or for method:
```cs
  [CLSCompliant(false)] 
```

Adding this attribute will add warnings during compilation if some CLS rules are broken.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
