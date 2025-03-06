---
date_added: 2025-03-06
tags:
  - csharp
---
Up: [Intermediate Language](Intermediate%20Language.md)
___
## Basic Instructions

- **`nop`**: No operation, does nothing (often used for debugging)
- **`ret`**: Returns from method
- **`br.s`/`brtrue.s`**: Branch instructions (short form) - conditional/unconditional jumps
- **`stloc.X`**: Store to local variable X
- **`ldloc.X`**: Load local variable X
- **`ldloca.s`**: Load address of local variable (short form)
- `ctor`: constructor
- `cctor` static constructior

>[!Info]
> destructors are represented in IL by the method with name `Finalize`

## Constants & Values

- **`ldc.i4.X`**: Load integer constant (X = 0, 1, 2, etc.)
- **`ldc.i4.s`**: Load integer constant (short form)
- **`ldstr`**: Load string literal

## Memory Operations

- **`ldind.u1`**: Load unsigned byte indirect from memory
- **`stind.i1`**: Store byte indirect into memory
- **`call`**: Call a method
- **`newobj`**: Create a new object

## Math & Logic

- **`add`**: Addition
- **`sub`**: Subtraction
- **`clt`**: Compare less than
- **`conv.u1`**: Convert to unsigned byte

## Method-Specific Operations

- **`Marshal::AllocHGlobal`**: Allocates unmanaged memory
- **`Marshal::FreeHGlobal`**: Frees unmanaged memory
- **`Span<Byte>::.ctor`**: Initializes a Span over unmanaged memory
- **`Span<Byte>::get_Item`**: Accesses an element in the Span
- **`Span<Byte>::get_Length`**: Gets the length of the Span
- **`DefaultInterpolatedStringHandler`**: Handles string interpolation

## Control Flow

- **`leave.s`**: Exit a protected region of code (try block)
- **`endfinally`**: End of finally block
- **`dup`**: Duplicate the value on top of stack
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
