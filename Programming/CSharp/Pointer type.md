---
date_added: 2025-01-22
tags:
  - csharp
---
Up: [[CTS]]
___
 ```cs
type* identifier;
void* identifier; //allowed but not recommended
```

>[!Info]
> - Methods, types, and code blocks can be defined as unsafe.
> - In some cases, unsafe code may increase an application's performance by removing array bounds checks.
> - Unsafe code is required when you call native functions that require pointers.
> - Using unsafe code introduces security and stability risks.
> - The code that contains unsafe blocks must be compiled with the [**AllowUnsafeBlocks**](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/compiler-options/language#allowunsafeblocks) compiler option.

Pointer types don't inherit from [Object](Object.md) and no conversions exist between pointer types and `object`

[[fixed]] can be used for variables will be pinned in memory and can't be moved by the garbage collector. 

[stackalloc](stackalloc.md) can be used to allocate memory on the stack. ````

```cs
Span<int> numbers = stackalloc int[length];
fixed (byte* pointerToFirst = numbers)
```


## Void pointer

void pointer (void*) makes no assumptions about the type of the underlying data
and is useful for functions that deal with raw memory

```cs
unsafe void Zap (void* memory, int byteCount)
{
	byte* b = (byte*)memory;
	for (int i = 0; i < byteCount; i++)
		*b++ = 0;
}
```

## Function pointer

Driectly points to a static methods. Mostly used in [Interoperability](Interoperability.md)
```cs
delegate*<int, char, string, void> // (void refers to the return type)

unsafe
{
	delegate*<string, int> functionPointer = &GetLength;
	int length = functionPointer ("Hello, world");
	static int GetLength (string s) => s.Length;
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
