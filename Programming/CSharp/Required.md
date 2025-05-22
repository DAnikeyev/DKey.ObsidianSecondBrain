---
date_added: 2025-01-13
tags:
  - dotnet
---
Up: [Field](Field.md)
___
 The `required` modifier indicates that the _field_ or _property_ it's applied to must be initialized by an [object initializer](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/object-and-collection-initializers).
```cs
public class Asset
{
	public required string Name;
	
	public Asset() { }
	
	[System.Diagnostics.CodeAnalysis.SetsRequiredMembers] // Lets the compiler know that this constructor sets required members.
	public Asset (string n) => Name = n;
}
```

```cs
Asset a1 = new Asset { Name = "House" }; // OK
Asset a2 = new Asset ("House"); // OK
Asset a3 = new Asset(); // Error!
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
