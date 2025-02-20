---
date_added: 2025-02-21
tags:
  - csharp
---
Up: [Modifiers](Modifiers.md)
___
 in a [[Field]] declaration indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class. A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.
A `readonly` field can't be assigned after the constructor exits. This rule has different implications for value types and reference types:

- Because value types directly contain their data, a field that is a `readonly` value type is immutable.
- Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object. That object might not be immutable. The `readonly` modifier prevents replacing the field value with a different instance of the reference type. However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.
- In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
