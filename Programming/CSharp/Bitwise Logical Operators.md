---
date_added: 2025-01-21
tags:
  - csharp
---
Up: [CSharp Operator](CSharp%20Operator.md)
___
 The bitwise and shift operators include unary bitwise complement, binary left and right shift, unsigned right shift, and the binary logical AND, OR, and exclusive OR operators. These operands take operands of the [integral numeric types](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) or the [char](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/char) type.

- Unary [`~` (bitwise complement)](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#bitwise-complement-operator-) operator
- Binary [`<<` (left shift)](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#left-shift-operator-), [`>>` (right shift)](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#right-shift-operator-), and [`>>>` (unsigned right shift)](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#unsigned-right-shift-operator-) operators
- Binary [`&` (logical AND)](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#logical-and-operator-), [`|` (logical OR)](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#logical-or-operator-), and [`^` (logical exclusive OR)](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/bitwise-and-shift-operators#logical-exclusive-or-operator-) operators
Those operators are defined for the `int`, `uint`, `long`, and `ulong` types. When both operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
