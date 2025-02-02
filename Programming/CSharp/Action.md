---
date_added: 2025-02-02
tags:
  - csharp
---
Up: [Delegate](Delegate.md)
___
 Encapsulates a [[Delegate]] method that has a single parameter and does not return a value
```cs
List<string> names = new List<string>();
names.Add("Bruce");
names.Add("Alfred");
names.Add("Tim");
names.Add("Richard");

// Display the contents of the list using the Print method.
names.ForEach(Print);

// The following demonstrates the anonymous method feature of C#
// to display the contents of the list to the console.
names.ForEach(delegate(string name)
{
    Console.WriteLine(name);
});

void Print(string s)
{
    Console.WriteLine(s);
}

/* This code will produce output similar to the following:
* Bruce
* Alfred
* Tim
* Richard
* Bruce
* Alfred
* Tim
* Richard
*/
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
