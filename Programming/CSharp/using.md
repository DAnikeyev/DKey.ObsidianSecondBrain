---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [CSharp Statement](CSharp%20Statement.md)
___
The `using` statement ensures the correct use of an [IDisposable](IDisposable.md) instance or await using for [IAsyncDisposable](IAsyncDisposable.md):

 ```csharp

var numbers = new List<int>();
using (StreamReader reader = File.OpenText("numbers.txt"))
{
    string line;
    while ((line = reader.ReadLine()) is not null)
    {
        if (int.TryParse(line, out int number))
        {
            numbers.Add(number);
        }
    }
}
 ```
You can also use a `using` _declaration_ that doesn't require braces.
```cs
using StreamReader numbersFile = File.OpenText("numbers.txt");
```
Or have multiple statements:
```cs
using (StreamReader numbersFile = File.OpenText("numbers.txt"), wordsFile = File.OpenText("words.txt"))
{
    // Process both files
}
```

Works also like that
```cs
StreamReader reader = File.OpenText(filePath);

using (reader)
{
    // Process file content
}
```

but might throw ObjectDisposedException after using block.

If [Exception](Exception.md) is thrown in the using block, the `Dispose` method is called before the exception is propagated.

```cs
using (var x = new Resource())
{
    throw new Exception();
}
// Equivalent to:
Resource x = new Resource();
try
{
    throw new Exception();
}
finally
{
    if (x != null)
    {
        ((IDisposable)x).Dispose();
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
