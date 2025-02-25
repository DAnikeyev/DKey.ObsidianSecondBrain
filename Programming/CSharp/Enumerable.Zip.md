---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
Applies a specified function to the corresponding elements of two sequences, producing a sequence of the results.

>[!Info]
> When the sequences are of different lengths, `Zip` stops when it reaches the end of the shorter sequence.
> 
```cs
public static System.Collections.Generic.IEnumerable<TResult> Zip<TFirst,TSecond,TResult>(this System.Collections.Generic.IEnumerable<TFirst> first, System.Collections.Generic.IEnumerable<TSecond> second, Func<TFirst,TSecond,TResult> resultSelector);
```

## Example
```cs
int[] numbers = { 1, 2, 3, 4 };
string[] words = { "one", "two", "three" };

var numbersAndWords = numbers.Zip(words, (first, second) => first + " " + second);

foreach (var item in numbersAndWords)
    Console.WriteLine(item);

// This code produces the following output:

// 1 one
// 2 two
// 3 three
```

>[!Info]
> Has an overload for three specified sequences.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
