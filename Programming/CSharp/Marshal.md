---
date_added: 2025-02-02
tags:
  - csharp
---
Up: [Interoperability](Interoperability.md)
___
 Marshalling is a way to transform data between parts of program, like [Managed code](Managed%20code.md) and [Unmanaged](Unmanaged.md)
## **Key Marshaling Attributes**:

- `[DllImport]`: Used to import native functions
- `[MarshalAs]`: Specifies how to marshal data types
- `[StructLayout]`: Controls how struct members are laid out in memory

##  **Important Marshaling Types**:

- `UnmanagedType.LPStr`: ANSI string (char*)
- `UnmanagedType.LPWStr`: Unicode string (wchar_t*)
- `UnmanagedType.BStr`: COM string
- `UnmanagedType.LPArray`: Arrays
- `UnmanagedType.ByValArray`: Fixed-size arrays
### Example:
```cs
using System.Runtime.InteropServices;

public class NativeInterop
{
    // Structure marshaling
    [StructLayout(LayoutKind.Sequential)]
    public struct NativeStruct
    {
        public int Id;
        [MarshalAs(UnmanagedType.LPWStr)]
        public string Name;
        [MarshalAs(UnmanagedType.ByValArray, SizeConst = 10)]
        public int[] Data;
    }

    // Function with various marshaling scenarios
    [DllImport("NativeLib.dll", CharSet = CharSet.Unicode, SetLastError = true)]
    public static extern bool ProcessData(
        [In] NativeStruct inputData,
        [Out] out NativeStruct outputData,
        [MarshalAs(UnmanagedType.LPWStr)] string description
    );

    public static void SafeNativeCall()
    {
        var input = new NativeStruct
        {
            Id = 1,
            Name = "Test",
            Data = new int[10]
        };
        NativeStruct output;

        try
        {
            bool success = ProcessData(input, out output, "Sample");
            if (!success)
            {
                int error = Marshal.GetLastWin32Error();
                throw new System.ComponentModel.Win32Exception(error);
            }
        }
        catch (Exception ex)
        {
            // Handle exceptions
            Console.WriteLine($"Error: {ex.Message}");
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
