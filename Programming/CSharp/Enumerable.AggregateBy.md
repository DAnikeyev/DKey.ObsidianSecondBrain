---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___

Close to [Enumerable.Aggregate](Enumerable.Aggregate.md), but groups aggregator by key selector, so hav features of [[Enumerable.GroupBy]].
```cs
using System;
using System.Collections.Generic;
using MoreLinq; // Ensure you have the MoreLinq package installed from NuGet

public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
}

public class Program
{
    public static void Main()
    {
        var people = new List<Person>
        {
            new Person { Name = "Alice", Age = 30 },
            new Person { Name = "Bob", Age = 30 },
            new Person { Name = "Charlie", Age = 40 },
            new Person { Name = "Dana", Age = 40 },
            new Person { Name = "Eve", Age = 30 },
        };

        /* 
         * Updated AggregateBy usage for efficiency:
         *
         * 1. keySelector (Func<Person, TKey>): Extracts the key from each element (p => p.Age).
         *
         * 2. accumulator (Func<Person, TAccumulate>): Creates an initial List<string> containing the person's name.
         *    p => new List<string> { p.Name }
         *
         * 3. merger (Func<TAccumulate, Person, TAccumulate>): Adds the current Person's name to the accumulated List<string>.
         *    (acc, p) => { acc.Add(p.Name); return acc; }
         *
         * 4. resultSelector (Func<TKey, TAccumulate, TResult>): Concatenates the list of names into a single string using string.Join.
         *    (age, namesList) => new { Age = age, Names = string.Join(", ", namesList) }
         */
        var aggregatedPeople = people.AggregateBy(
            keySelector: p => p.Age,
            accumulator: p => new List<string> { p.Name },
            merger: (acc, p) => { acc.Add(p.Name); return acc; },
            resultSelector: (age, namesList) => new { Age = age, Names = string.Join(", ", namesList) }
        );

        foreach (var group in aggregatedPeople)
        {
            Console.WriteLine($"Age: {group.Age}, Names: {group.Names}");
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
