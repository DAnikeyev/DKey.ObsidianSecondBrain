---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
 Projects each element of a sequence to an [Generic IEnumerable](Generic%20IEnumerable.md) and flattens the resulting sequences into one sequence. Has an optional TResultSelector
###  Example
```cs
List<User> users = new List<User>
            {
                new User { Name = "Alice", Hobbies = new List<string> { "Reading", "Hiking", "Cooking" } },
                new User { Name = "Bob", Hobbies = new List<string> { "Gaming", "Cycling" } },
                new User { Name = "Charlie", Hobbies = new List<string> { "Swimming" } }
            };

            // Use SelectMany to flatten the hobbies arrays and project the user and hobby details.
            IEnumerable<TResult> userHobbies = users.SelectMany(
                user => user.Hobbies, 
                (user, hobby) => new TResult { UserName = user.Name, Hobby = hobby }
            );
```

>[!Info]
> selector `user => user.Hobbies` could also parse index `(user, index) => something`
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
