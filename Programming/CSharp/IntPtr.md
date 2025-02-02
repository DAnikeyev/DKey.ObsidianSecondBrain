---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [Value Type](Value%20Type.md)
___

IntPtr is a sage type, but usually used in [[unsafe]] situation, like [Interoperability](Interoperability.md) scenarious() calling [unmanaged](Unmanaged.md) code)
```cs
using System;

class Program
{
    static void Main()
    {
        // Create an IntPtr from an integer
        IntPtr pointer = new IntPtr(123456);

        // Check if the pointer is not zero
        if (pointer != IntPtr.Zero)
        {
            Console.WriteLine("Pointer is not null.");
        }

        // Convert IntPtr back to an integer
        int intValue = pointer.ToInt32();
        Console.WriteLine("Integer value: " + intValue);
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
