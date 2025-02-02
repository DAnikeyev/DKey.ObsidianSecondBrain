---
date_added: 2025-02-02
tags:
  - csharp
---
Up: [Delegate](Delegate.md)
___
 Encapsulates a method that has no parameters and returns a value of the type specified by the `TResult` parameter.
 ```cs
 // Declare a Func variable and assign a lambda expression to the
// variable. The method takes a string and converts it to uppercase.
Func<string, string> selector = str => str.ToUpper();

// Create an array of strings.
string[] words = { "orange", "apple", "Article", "elephant" };
// Query the array and select strings according to the selector method.
IEnumerable<String> aWords = words.Select(selector);

// Output the results to the console.
foreach (String word in aWords)
    Console.WriteLine(word);

/*
This code example produces the following output:

ORANGE
APPLE
ARTICLE
ELEPHANT

*/
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
