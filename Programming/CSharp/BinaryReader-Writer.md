---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [System.IO](System.IO.md) [TextReader-Writer](TextReader-Writer.md)
___
Writes primitive types in binary to a stream and supports and reading writing strings in a specific encoding.

 ```cs
using System;
using System.IO;
using System.Text;

class ConsoleApplication
{
    const string fileName = "AppSettings.dat";

    static void Main()
    {
        WriteDefaultValues();
        DisplayValues();
    }

    public static void WriteDefaultValues()
    {
        using (var stream = File.Open(fileName, FileMode.Create))
        {
            using (var writer = new BinaryWriter(stream, Encoding.UTF8, false))
            {
                writer.Write(1.250F);
                writer.Write(@"c:\Temp");
                writer.Write(10);
                writer.Write(true);
            }
        }
    }

    public static void DisplayValues()
    {
        float aspectRatio;
        string tempDirectory;
        int autoSaveTime;
        bool showStatusBar;

        if (File.Exists(fileName))
        {
            using (var stream = File.Open(fileName, FileMode.Open))
            {
                using (var reader = new BinaryReader(stream, Encoding.UTF8, false))
                {
                    aspectRatio = reader.ReadSingle();
                    tempDirectory = reader.ReadString();
                    autoSaveTime = reader.ReadInt32();
                    showStatusBar = reader.ReadBoolean();
                }
            }

            Console.WriteLine("Aspect ratio set to: " + aspectRatio);
            Console.WriteLine("Temp directory is: " + tempDirectory);
            Console.WriteLine("Auto save time set to: " + autoSaveTime);
            Console.WriteLine("Show status bar: " + showStatusBar);
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
