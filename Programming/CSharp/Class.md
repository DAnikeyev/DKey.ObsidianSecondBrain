---
date_added: 2025-01-12
tags:
  - csharp
sr-due: 2025-03-29
sr-interval: 4
sr-ease: 270
---
Up: [Reference Type](Reference%20Type.md)
___
is a [[Reference Type]] that can be derived from any other type and is implicitly derived from [[Object]].
``` csharp
//[access modifier] - [class] - [identifier]
public class Customer
{
   // Fields, properties, methods and events go here...
}
```


>[!info]
> - Declarations in classes can have various [[Access modifiers]]
> - Class can be [[Public]] or [[Internal]] (Internal by default))
> - Can have [[Generic Constraint]]

## Declarations in class

- [[Constructor]]
- [[Constant]]
- [[Field]]
- [[Method]]
- [[Finalizer]]
- [[Property]]
- [[CSharp Indexer|Indexer]]
- [[CSharp Operator|Operator]]
- [[Event]]
- [Delegate](Delegate.md)
## Optional Characteristics

 - Sealed: Cannot be inherited
 - Implements: class implements 1 or more interfaces
 - Abstract: Cannot be instantiated
 - Inherits: class inherits from 1 base class
 - Exported: class is visible outside of the assembly
 - Nested: class is defined within another class
 - [[Generic type parameters]]
 >[!Info]
>Class can implement any number of interfaces and no more than 1 base class
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
