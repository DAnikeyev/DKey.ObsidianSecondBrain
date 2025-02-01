---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [System.IO](System.IO.md)
___
[StringReader](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringreader?view=net-9.0) enables you to read a string synchronously or asynchronously. You can read a character at a time with the [Read](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringreader.read?view=net-9.0) or the [ReadAsync](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringreader.readasync?view=net-9.0) method, a line at a time using the [ReadLine](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringreader.readline?view=net-9.0) or the [ReadLineAsync](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringreader.readlineasync?view=net-9.0) method and an entire string using the [ReadToEnd](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringreader.readtoend?view=net-9.0) or the [ReadToEndAsync](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringreader.readtoendasync?view=net-9.0) method.

[StringWriter](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringwriter?view=net-9.0) enables you to write to a string synchronously or asynchronously. You can write a character at a time with the [Write(Char)](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringwriter.write?view=net-9.0#system-io-stringwriter-write(system-char)) or the [WriteAsync(Char)](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringwriter.writeasync?view=net-9.0#system-io-stringwriter-writeasync(system-char)) method, a string at a time using the [Write(String)](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringwriter.write?view=net-9.0#system-io-stringwriter-write(system-string)) or the [WriteAsync(String)](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringwriter.writeasync?view=net-9.0#system-io-stringwriter-writeasync(system-string)) method. In addition, you can write a character, an array of characters or a string followed by the line terminator asynchronously with one of the [WriteLineAsync](https://learn.microsoft.com/en-us/dotnet/api/system.io.stringwriter.writelineasync?view=net-9.0) methods.

```cs
using System;
using System.IO;

class StringRW
{
    static void Main()
    {
        string textReaderText = "TextReader is the abstract base " +
            "class of StreamReader and StringReader, which read " +
            "characters from streams and strings, respectively.\n\n" +

            "Create an instance of TextReader to open a text file " +
            "for reading a specified range of characters, or to " +
            "create a reader based on an existing stream.\n\n" +

            "You can also use an instance of TextReader to read " +
            "text from a custom backing store using the same " +
            "APIs you would use for a string or a stream.\n\n";

        Console.WriteLine("Original text:\n\n{0}", textReaderText);

        // From textReaderText, create a continuous paragraph
        // with two spaces between each sentence.
        string aLine, aParagraph = null;
        StringReader strReader = new StringReader(textReaderText);
        while(true)
        {
            aLine = strReader.ReadLine();
            if(aLine != null)
            {
                aParagraph = aParagraph + aLine + " ";
            }
            else
            {
                aParagraph = aParagraph + "\n";
                break;
            }
        }
        Console.WriteLine("Modified text:\n\n{0}", aParagraph);

        // Re-create textReaderText from aParagraph.
        int intCharacter;
        char convertedCharacter;
        StringWriter strWriter = new StringWriter();
        strReader = new StringReader(aParagraph);
        while(true)
        {
            intCharacter = strReader.Read();

            // Check for the end of the string
            // before converting to a character.
            if(intCharacter == -1) break;

            convertedCharacter = (char)intCharacter;
            if(convertedCharacter == '.')
            {
                strWriter.Write(".\n\n");

                // Bypass the spaces between sentences.
                strReader.Read();
                strReader.Read();
            }
            else
            {
                strWriter.Write(convertedCharacter);
            }
        }
        Console.WriteLine("\nOriginal text:\n\n{0}",
            strWriter.ToString());
    }
}
```

>[!Info]
> does not actually have any resources to dispose. This means that disposing it is not necessary.


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
