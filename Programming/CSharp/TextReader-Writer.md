---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [CSharp](CSharp.md)
___
 Implements [IDisposable](IDisposable.md). It's an abstract class for other ReaderWriters:
```cs
using System.IO;

namespace ConsoleApplication
{
    class Program4
    {
        static void Main()
        {
            WriteCharacters();
        }

        static async void WriteCharacters()
        {
            using (StreamWriter writer = File.CreateText("newfile.txt"))
            {
                await writer.WriteLineAsync("First line of example");
                await writer.WriteLineAsync("and second line");
            }
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
