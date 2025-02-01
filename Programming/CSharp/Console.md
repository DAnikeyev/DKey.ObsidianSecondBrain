---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [CSharp](CSharp.md)
___
Represents the standard input, output, and error streams for console applications. This class cannot be inherited.

#### Methods

1. **Write**:
    
    - Writes text to the console without a newline.
    - Example: `Console.Write("Hello, World!")`.
2. **WriteLine**:
    
    - Writes text to the console followed by a newline.
    - Example: `Console.WriteLine("Hello, World!")`.
3. **Read**:
    
    - Reads the next character from the standard input stream.
    - Example: `int input = Console.Read();`.
4. **ReadLine**:
    
    - Reads the next line of characters from the standard input stream.
    - Example: `string input = Console.ReadLine();`.
5. **Clear**:
    
    - Clears the console buffer and corresponding console window of display information.
    - Example: `Console.Clear();`.
6. **SetCursorPosition**:
    
    - Sets the position of the cursor in the console window.
    - Example: `Console.SetCursorPosition(0, 0);`.
7. **Beep**:
    
    - Plays a beep sound through the console speaker.
    - Example: `Console.Beep();`.
8. **OpenStandardInput**, **OpenStandardOutput**, **OpenStandardError**:
    
    - Opens the standard input, output, or error stream.
    - Example: `Stream inputStream = Console.OpenStandardInput();`.

## Redirecting using `SetOut` method:
```cs
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a StringWriter to capture the console output
        using (StringWriter stringWriter = new StringWriter())
        {
            // Redirect console output to the StringWriter
            Console.SetOut(stringWriter);

            // Write some output to the console (which is now captured by the StringWriter)
            Console.WriteLine("This output is captured in a string.");

            // Retrieve the captured output as a string
            string capturedOutput = stringWriter.ToString();

            // Display the captured output
            Console.WriteLine("Captured Output:");
            Console.WriteLine(capturedOutput);
        }

        // After the using block, the StringWriter is disposed, and the console output is reset
        Console.WriteLine("This output will appear in the console again.");
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
