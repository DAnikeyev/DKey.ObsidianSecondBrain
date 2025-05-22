---
date_added: 2025-01-23
tags:
  - csharp
---
Up: [Value Type](Value%20Type.md)
___
 
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
You use the `record` modifier to define a [Reference Type](Reference%20Type.md)that provides built-in functionality for encapsulating data. The `record class` syntax as a synonym to clarify a reference type, and `record struct` to define a [Value Type](Value%20Type.md)with similar functionality.

>[!Important]
> Unless {get; set;} is specified, all properties are `init-only` and can only be set during object initialization. This is similar to the `readonly` modifier for fields.
## Record class

```cs
public readonly record struct Point(double X, double Y, double Z);
//Or
public record Person
{
    public required string FirstName { get; init; }
    public required string LastName { get; init; }
};
```

## Record struct

```cs
public record struct Person(string FirstName, string LastName);
//Or
public record struct Point
{
    public double X { get; init; }
    public double Y { get; init; }
    public double Z { get; init; }
}
```

# Features:
### Value Equality
 two records are equal if all their properties are equal.
 
### Non-destructive Mutation
  A record is immutable, but you can create a new record with the same properties as the original record, with one or more properties changed equivalent to [Nondestructive struct mutation](Nondestructive%20struct%20mutation.md)

### Built-in formatting
Records have a compile-generated `ToString()` method that returns a string representation of the record.

### Inheritance
A record can inherit from another record. However, a record can't inherit from a class, and a class can't inherit from a record.