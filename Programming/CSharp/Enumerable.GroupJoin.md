---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
## Arguments
- outer: The first sequence to join.
- inner: The sequence to join to the first sequence.
- outerKeySelector: A function to extract the join key from each element of the first sequence.
- innerKeySelector: A function to extract the join key from each element of the second sequence.
- resultSelector:  `Func <Touter, IEnumerable <TInner>, TResult>` A function to create a result element from an element from the first sequence and a collection of matching elements from the second sequence.

This method is implemented by using deferred execution. The immediate return value is an object that stores all the information that is required to perform the action. The query represented by this method is not executed until the object is enumerated either by calling its `GetEnumerator` method directly or by using `foreach` in C#.

>[!Info]
> If there are no correlated elements in `inner` for a given element of `outer`, the sequence of matches for that element will be empty but will still appear in the results.
### Example
```cs
var query =
        people.GroupJoin(pets,
                         person => person,
                         pet => pet.Owner,
                         (person, petCollection) =>
                             new
                             {
                                 OwnerName = person.Name,
                                 Pets = petCollection.Select(pet => pet.Name)
                             });

    foreach (var obj in query)
    {
        // Output the owner's name.
        Console.WriteLine("{0}:", obj.OwnerName);
        // Output each of the owner's pet's names.
        foreach (string pet in obj.Pets)
        {
            Console.WriteLine("  {0}", pet);
        }
    }
```

>[!Info]
> GroupJoin has no direct equivalent in traditional relational database terms. However, this method does implement a superset of inner joins and left outer joins.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
