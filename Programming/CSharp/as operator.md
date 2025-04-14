---
date_added: 2025-04-01
tags:
  - csharp
---
Up: [Casting operator](Casting%20operator.md) [keyword](keyword.md)
___
The `as` operator explicitly converts the result of an expression to a given reference or nullable value type. If the conversion isn't possible, the `as` operator returns `null`
#### `as` Operator
- **Usage**: `InterfaceType b = a as InterfaceType;`
- **Returns**: `null` if conversion fails.
- **Compatibility**: Only works with reference types and nullable types.
- **Safety**: Safer as it doesn't throw exceptions.
- **Performance**: More performant as it avoids exception handling.

#### Direct Cast
- **Usage**: `InterfaceType b = (InterfaceType)a;`
- **Throws**: `InvalidCastException` if conversion fails.
- **Compatibility**: Works with both value types and reference types.
- **Strictness**: More strict, forces the conversion.
- **Performance**: Less performant when conversion fails due to exception handling.

```cs
E as T
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
