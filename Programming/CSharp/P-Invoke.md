---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Interoperability](Interoperability.md)
___
P/Invoke is a technology that allows you to access structs, callbacks, and functions in unmanaged libraries from your [managed code](Managed%20code.md).

Example: 
```cs
// Use DllImport to import the Win32 MessageBox function.
    [DllImport("user32.dll", CharSet = CharSet.Unicode)]
    public static extern int MessageBox(IntPtr hWnd, String text, String caption, uint type);
```

On dot Net6+ you can write
```cs
using System;
using System.Runtime.InteropServices;

public partial class Program
{
    // Import user32.dll (containing the function we need) and define
    // the method corresponding to the native function.
    [LibraryImport("user32.dll", StringMarshalling = StringMarshalling.Utf16, SetLastError = true)]
    private static partial int MessageBox(IntPtr hWnd, string lpText, string lpCaption, uint uType);

    public static void Main(string[] args)
    {
        // Invoke the function as a regular managed method.
        MessageBox(IntPtr.Zero, "Command-line message box", "Attention!", 0);
    }
}
```
## Visibility in dll for cpp
extern "C" __declspec(dllexport) void __stdcall MyFunction() {
    // code
}
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
