---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [[Class]]
___
 It's a member that provides a way to read, write, or compute the value of the field.
## Auto-implemented properties
 ```cs
 public class Person
{
    public string? FirstName { get; set; }

    // Omitted for brevity.
}
```
# Required properties
```cs
public class Person
{
    public Person() { }

    [SetsRequiredMembers]
    public Person(string firstName) => FirstName = firstName;

    public required string FirstName { get; init; }

    // Omitted for brevity.
}
```

- Accessors a can be made private 

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
