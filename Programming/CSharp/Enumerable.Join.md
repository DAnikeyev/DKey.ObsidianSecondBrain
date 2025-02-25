---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [[Enumerable]]
___
 Arguments
- outer: The first sequence to join.
- inner: The sequence to join to the first sequence.
- outerKeySelector: A function to extract the join key from each element of the first sequence.
- innerKeySelector: A function to extract the join key from each element of the second sequence.
- resultSelector:  `Func <Touter, IEnumerable <TInner>, TResult>` A function to create a result element from an element from the first sequence and a collection of matching elements from the second sequence.

This method is implemented by using deferred execution. The immediate return value is an object that stores all the information that is required to perform the action. The query represented by this method is not executed until the object is enumerated either by calling its `GetEnumerator` method directly or by using `foreach` in C#.

```cs

    // Create a list of Person-Pet pairs where
    // each element is an anonymous type that contains a
    // Pet's name and the name of the Person that owns the Pet.
    var query =
        people.Join(pets,
                    person => person,
                    pet => pet.Owner,
                    (person, pet) =>
                        new { OwnerName = person.Name, Pet = pet.Name });

    foreach (var obj in query)
    {
        Console.WriteLine(
            "{0} - {1}",
            obj.OwnerName,
            obj.Pet);
    }
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
