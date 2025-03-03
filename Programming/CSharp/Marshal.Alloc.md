---
date_added: 2025-03-03
tags:
  - csharp
---
Up: [Marshal](Marshal.md)
___

Allows to allocate unmanaged memory.
 ```cs
   
public void Run()  
{  
    _unmanagedResource = Marshal.AllocHGlobal(100); // Allocate 100 bytes of unmanaged memory  
}  
  
private void ReleaseUnmanagedResources()  
{  
    if (_unmanagedResource != IntPtr.Zero)  
    {        Marshal.FreeHGlobal(_unmanagedResource);  
        _unmanagedResource = IntPtr.Zero;  
    }
}
...
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
