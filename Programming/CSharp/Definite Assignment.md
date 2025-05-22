---
date_added: 2025-05-19
tags:
  - csharp
---
Up: [Compilation process](Compilation%20process.md)
___
 C# enforces a definite assignment policy. In practice, this means that outside of
an [unsafe](unsafe.md) or [Interoperability](Interoperability.md) context, you can’t accidentally access uninitialized memory.
Definite assignment has three implications:
	- Local variables must be assigned a value before they can be read.
	• Function arguments must be supplied when a method is called 
	• All other variables (such as fields and array elements) are automatically initialized
by the runtime.
For example, the following code results in a compile-time error:
 ```csharp
	 int x;
	Console.WriteLine (x); // Compile-time error
 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
