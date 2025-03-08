---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Stream](Stream.md)
___
 StreamReader is designed for character input in a particular encoding, whereas the Stream class is designed for byte input and output.

>[!Info]
> Flush() writes any buffered data to the underlying stream. It is called automatically when the StreamWriter is disposed of, so there is no need to call it explicitly.


 
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
- **FileStream**: Use this when you need to perform low-level operations on files, such as reading or writing bytes. It's useful when you need more control over how data is read from or written to a file, such as when dealing with binary data.
    
- **StreamReader**: Use this when you need to read text from a file. It provides methods for reading characters, lines, and the entire content of a file as a string, handling character encoding automatically.
    
- **StreamWriter**: Use this when you need to write text to a file. It handles character encoding and provides methods for writing characters, strings, and lines to a file.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
