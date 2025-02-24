---
date_added: 2025-02-21
tags:
  - csharp
---
Up: [SpecializedCollection](SpecializedCollection.md)
___
Represents an indexed collection of key/value pairs.

```cs
class App
{
    static void Main()
    {
        People peopleCollection = new People(3);
        peopleCollection.Add("John", "Smith");
        peopleCollection.Add("Jim", "Johnson");
        peopleCollection.Add("Sue", "Rabon");

        Console.WriteLine("Displaying the entries in peopleCollection:");
        foreach (DictionaryEntry de in peopleCollection)
        {
            Console.WriteLine("{0} {1}", de.Key, de.Value);
        }

        Console.WriteLine();
        Console.WriteLine("Displaying the entries in the modified peopleCollection:");
        peopleCollection["Jim"] = "Jackson";
        peopleCollection.Remove("Sue");
        peopleCollection.Insert(0, "Fred", "Anderson");

        foreach (DictionaryEntry de in peopleCollection)
        {
            Console.WriteLine("{0} {1}", de.Key, de.Value);
        }
    }
}
/* This code produces output similar to the following:
 *
 * Displaying the entries in peopleCollection:
 * John Smith
 * Jim Johnson
 * Sue Rabon
 *
 * Displaying the entries in the modified peopleCollection:
 * Fred Anderson
 * John Smith
 * Jim Jackson
 */
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
