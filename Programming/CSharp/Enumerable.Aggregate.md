---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
 ```cs
 public static TResult Aggregate<TSource,TAccumulate,TResult>(this System.Collections.Generic.IEnumerable<TSource> source, TAccumulate seed, Func<TAccumulate,TSource,TAccumulate> func, Func<TAccumulate,TResult> resultSelector);
 
```
## Arguments

 - source: collection
 - seed (optional): initial value of accumulator.
 - func: accumulator
 - resultSelector: converts final result
## Example
```cs
string[] fruits = { "apple", "mango", "orange", "passionfruit", "grape" };

// Determine whether any string in the array is longer than "banana".
string longestName =
    fruits.Aggregate("banana",
                    (longest, next) =>
                        next.Length > longest.Length ? next : longest,
                    // Return the final result as an upper case string.
                    fruit => fruit.ToUpper());

Console.WriteLine(
    "The fruit with the longest name is {0}.",
    longestName);

// This code produces the following output:
//
// The fruit with the longest name is PASSIONFRUIT.
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
