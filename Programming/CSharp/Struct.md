---
date_added: 2025-01-20
tags:
  - csharp
sr-due: 2025-04-05
sr-interval: 4
sr-ease: 287
---
Up: [Value Type](Value%20Type.md)
___
 Is a [Value Type](Value%20Type.md) that encapsulate data and functionality. Variable values are copied on the assignment.

## Content

- [Value Type](Value%20Type.md) or [Reference Type](Reference%20Type.md) [Field](Field.md) with optional [Access modifiers](Access%20modifiers.md)
- [[Method]]
- [Property](Property.md)
- [[CSharp Indexer|Indexer]]
- [[CSharp Operator|Operator]]
- [Constructor](Constructor.md)
- [Event](Event)
- [Interface](Interface.md) inheritance

>[!Info]
> - Can't Inherit from another struct or class
> - Can't have [[Destructor|Destructors]]
> - All [Field](Field.md) must be initialized until the end of the constructor

## Read-only struct

If struct is declared as [Readonly](Readonly), all data members are read-only and all [[Property|Properties]] should be read-only or init only.

>[!Info]
>In a `readonly` struct, a data member of a mutable reference type still can mutate its own state. For example, you can't replace a [List](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1) instance, but you can add new elements to it.

## Allocation

- Are allocated on [Memory stack](Memory%20stack.md) by default
- When [[Boxing and Unboxing|boxed]] or part of [Reference Type](Reference%20Type.md) are allocated on heap
- Passing struct by ==ref== allows to change struct without copying
- If struct contains [Reference Type](Reference%20Type.md) members, it combines the behaviour of [Value Type](Value%20Type.md) and [Reference Type](Reference%20Type.md) so using such structs requires careful design to avoid unintended consequences.

  
For large data structures, using a class is often more efficient because:
- It avoids the overhead of copying large amounts of data.
- It leverages the heap's ability to handle larger memory allocations.
- It benefits from the garbage collector's memory management capabilities.
# Links

```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
