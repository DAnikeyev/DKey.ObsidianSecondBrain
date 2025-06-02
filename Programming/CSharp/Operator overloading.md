---
date_added: 2025-02-27
tags:
  - csharp
---
Up: [CSharp Operator](CSharp%20Operator.md)
___
## Examples:
```cs
public struct Fahrenheit
{
    public double Degrees { get; }

    public Fahrenheit(double degrees)
    {
        Degrees = degrees;
    }

    // Implicit conversion from Fahrenheit to Celsius
    public static implicit operator Celsius(Fahrenheit f)
    {
        return new Celsius((f.Degrees - 32) * 5 / 9);
    }
}

public struct Celsius
{
    public double Degrees { get; }

    public Celsius(double degrees)
    {
        Degrees = degrees;
    }

    // Implicit conversion from Celsius to Fahrenheit
    public static implicit operator Fahrenheit(Celsius c)
    {
        return new Fahrenheit(c.Degrees * 9 / 5 + 32);
    }
}

// Usage
Fahrenheit f = new Fahrenheit(98.6);
Celsius c = f; // Implicit conversion
```

### Arithmetic Operators

- `+` (addition)
- `-` (subtraction)
- `*` (multiplication)
- `/` (division)
- `%` (modulus)

### Unary Operators

- `+` (unary plus)
- `-` (unary negation)
- `!` (logical negation)
- `~` (bitwise complement)
- `++` (increment)
- `--` (decrement)
- `true` and `false` (used to define the true and false values for a type)

### Comparison Operators

- `==` (equality)
- `!=` (inequality)
- `<` (less than)
- `>` (greater than)
- `<=` (less than or equal to)
- `>=` (greater than or equal to)

### Logical and Bitwise Operators

- `&` (logical AND, bitwise AND)
- `|` (logical OR, bitwise OR)
- `^` (logical XOR, bitwise XOR)

### Shift Operators

- `<<` (left shift)
- `>>` (right shift)

### Other Operators

- `[]` (indexer, though technically not overloaded with the `operator` keyword, you can define custom indexers in your classes)
- `()` (invocation, similar to indexers, you can define custom behavior for function calls in classes)
- `->` (pointer member access, used in unsafe code)
- `new` (allocation, though not overloadable, you can define custom behavior in constructors)

### Conversion Operators

- `implicit` (for defining implicit conversions)
- `explicit` (for defining explicit conversions)

## Can't overload these operators:
1. **Assignment Operator**: =
2. **Conditional Logical Operators**: `&&`, `||`
3. **Equality Operators**: ==, != (Note: You can overload these, but you must overload them in pairs)
4. **Member Access Operators**: `.`, `->`
5. **Type Operators**: `is`, `as`
6. **Conditional Operator**: `?:`
7. **Null Coalescing Operator**: `??`
8. **New Operator**: `new`
9. **Typeof Operator**: `typeof`
10. **Sizeof Operator**: `sizeof`
11. **Checked and Unchecked Operators**: `checked`, `unchecked`
12. **Nameof Operator**: `nameof`
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
