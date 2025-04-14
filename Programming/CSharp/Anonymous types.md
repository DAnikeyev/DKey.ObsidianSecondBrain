---
date_added: 2025-01-30
tags:
  - csharp
---
Up: [Other CSharp Features](Other%20CSharp%20Features.md)
___
 Encapsulation of readonly properties

- **Class-based**: Anonymous types are always classes, not structs or any other type.
- **Immutable**: Once created, the properties of an anonymous type cannot be changed.
- **Read-only properties**: The properties are read-only and are automatically given public getters.
- **Compiler-generated**: The compiler generates a class with the appropriate properties and overrides for `ToString()`, `Equals()`, and `GetHashCode()`. (Similar to [Record](Record.md))
 ```cs
 var v = new { Amount = 108, Message = "Hello" };

// Rest the mouse pointer over v.Amount and v.Message in the following
// statement to verify that their inferred types are int and string.
Console.WriteLine(v.Amount + v.Message);
```

```cs
var people = new[] { new { Name = "Alice", Age = 30 }, new { Name = "Bob", Age = 25 } }; var names = people.Select(person => new { person.Name });
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
