---
date_added: 2025-02-19
tags:
  - csharp
---
Up: [Fundamental Interfaces](Fundamental%20Interfaces.md)
___
 Supports cloning, which creates a new instance of a class with the same value as an existing instance.

```cs
using System;

public class Person : ICloneable
{
    public string Name { get; set; }
    public int Age { get; set; }

    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }

    // Implement the Clone method
    public object Clone()
    {
        // Perform a shallow copy
        return this.MemberwiseClone();
    }
}

class Program
{
    static void Main()
    {
        Person original = new Person("Alice", 30);
        Person clone = (Person)original.Clone();

        Console.WriteLine($"Original: {original.Name}, {original.Age}");
        Console.WriteLine($"Clone: {clone.Name}, {clone.Age}");

        // Modify the clone
        clone.Name = "Bob";
        clone.Age = 25;

        Console.WriteLine($"After modification:");
        Console.WriteLine($"Original: {original.Name}, {original.Age}");
        Console.WriteLine($"Clone: {clone.Name}, {clone.Age}");
    }
}
```
## Methods:

|   |   |
|---|---|
|[Clone()](https://learn.microsoft.com/en-us/dotnet/api/system.icloneable.clone?view=net-9.0#system-icloneable-clone)|Creates a new object that is a copy of the current instance.|


## Applies to
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
