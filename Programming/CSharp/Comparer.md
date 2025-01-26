---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
 ```cs
 using System;
using System.Collections.Generic;

public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
}

public class Program
{
    public static void Main()
    {
        List<Person> people = new List<Person>
        {
            new Person { Name = "Alice", Age = 30 },
            new Person { Name = "Bob", Age = 25 },
            new Person { Name = "Charlie", Age = 35 }
        };

        // Define a comparer on the fly using a lambda expression
        people.Sort((x, y) => x.Age.CompareTo(y.Age));

        foreach (var person in people)
        {
            Console.WriteLine($"{person.Name}, {person.Age}");
        }
    }
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
