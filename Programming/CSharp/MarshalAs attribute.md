---
date_added: 2025-03-06
tags:
  - csharp
---
Up: [Common attributes](Common%20attributes.md) [Marshal](Marshal.md)
___
Indicates how to marshal the data between managed and unmanaged code.

```cs
using System;
using System.Text;
using System.Runtime.InteropServices;

class Program
{

//Applied to a parameter.
  public void M1([MarshalAs(UnmanagedType.LPWStr)]String msg) {}

//Applied to a field within a class.
  class MsgText {
                [MarshalAs(UnmanagedType.LPWStr)]
                public String msg = "Hello World";
                }

//Applied to a return value.
[return: MarshalAs(UnmanagedType.LPWStr)]
    public String GetMessage()
    {
        return "Hello World";
    }

static void Main(string[] args)
    {  }
}
```

For mapping, [[Unmanaged type enum]] is used
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
