---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
Helps to operate in place on data in memory. It's allocation-free representation of continuous memory.
Can't be used in lambdas or async methods.

Can also refer to data on stack using [stackalloc](stackalloc.md) keyword.

```cs
Span<byte> bytes = stackalloc byte[2];
```

use AsSpan() for collections like that:
```cs
Span<int> span = CollectionsMarshal.AsSpan(list);
```
### What is inside span:
```cs
public readonly ref struct Span<T>
{
  private readonly ref T _pointer;
  private readonly int _length;
  ...
}
```

### Example: [[Marshal]]
Can work with Marshal and Interop services.

```cs
IntPtr ptr = Marshal.AllocHGlobal(1);
try
{
  Span<byte> bytes;
  unsafe { bytes = new Span<byte>((byte*)ptr, 1); }
  bytes[0] = 42;
  Assert.Equal(42, bytes[0]);
  Assert.Equal(Marshal.ReadByte(ptr), bytes[0]);
  bytes[1] = 43; // Throws IndexOutOfRangeException
}
finally { Marshal.FreeHGlobal(ptr); }
```

### Example: Reading from [Unmanaged](Unmanaged.md)
  
Imagine you have a C function like this:

```c
// Example native function that fills a buffer with data
void FillBuffer(unsigned char* buffer, int length) {
    for (int i = 0; i < length; i++) {
        buffer[i] = (unsigned char)(i % 256);
    }
}
```

#### Interop in C#

You can use [P-Invoke](P-Invoke.md) to call this function from C# and use `Span<byte>` to work with the buffer:

```csharp
using System;
using System.Runtime.InteropServices;

class Program
{
    // P/Invoke declaration for the native function
    [DllImport("NativeLibrary.dll", CallingConvention = CallingConvention.Cdecl)]
    private static extern void FillBuffer(IntPtr buffer, int length);

    static void Main()
    {
        int length = 100;
        IntPtr unmanagedBuffer = Marshal.AllocHGlobal(length);

        try
        {
            // Call the native function to fill the buffer
            FillBuffer(unmanagedBuffer, length);

            // Create a Span<byte> over the unmanaged memory
            Span<byte> span = new Span<byte>((void*)unmanagedBuffer, length);

            // Use the Span<byte> to process the data
            for (int i = 0; i < span.Length; i++)
            {
                Console.WriteLine($"Byte {i}: {span[i]}");
            }
        }
        finally
        {
            // Free the unmanaged memory
            Marshal.FreeHGlobal(unmanagedBuffer);
        }
    }
}
```

## Constructors

|   |   |
|---|---|
|[Span<T>(T)](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.-ctor?view=net-9.0#system-span-1-ctor(-0@))|Creates a new [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0) of length 1 around the specified reference.|
|[Span<T>(T[], Int32, Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.-ctor?view=net-9.0#system-span-1-ctor(-0()-system-int32-system-int32))|Creates a new [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0) object that includes a specified number of elements of an array starting at a specified index.|
|[Span<T>(T[])](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.-ctor?view=net-9.0#system-span-1-ctor(-0()))|Creates a new [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0) object over the entirety of a specified array.|
|[Span<T>(Void*, Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.-ctor?view=net-9.0#system-span-1-ctor(system-void*-system-int32))|Creates a new [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0) object from a specified number of `T` elements starting at a specified memory address.|

## Properties

|   |   |
|---|---|
|[Empty](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.empty?view=net-9.0#system-span-1-empty)|Returns an empty [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0) object.|
|[IsEmpty](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.isempty?view=net-9.0#system-span-1-isempty)|Returns a value that indicates whether the current [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0) is empty.|
|[Item[Int32]](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.item?view=net-9.0#system-span-1-item(system-int32))|Gets the element at the specified zero-based index.|
|[Length](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.length?view=net-9.0#system-span-1-length)|Returns the length of the current span.|

## Methods

|   |   |
|---|---|
|[Clear()](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.clear?view=net-9.0#system-span-1-clear)|Clears the contents of this [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0) object.|
|[CopyTo(Span<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.copyto?view=net-9.0#system-span-1-copyto(system-span((-0))))|Copies the contents of this [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0) into a destination [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0).|
|[Equals(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.equals?view=net-9.0#system-span-1-equals(system-object))|**Obsolete.**<br><br>Calls to this method are not supported.|
|[Fill(T)](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.fill?view=net-9.0#system-span-1-fill(-0))|Fills the elements of this span with a specified value.|
|[GetEnumerator()](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.getenumerator?view=net-9.0#system-span-1-getenumerator)|Returns an enumerator for this [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0).|
|[GetHashCode()](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.gethashcode?view=net-9.0#system-span-1-gethashcode)|**Obsolete.**<br><br>Throws a [NotSupportedException](https://learn.microsoft.com/en-us/dotnet/api/system.notsupportedexception?view=net-9.0).|
|[GetPinnableReference()](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.getpinnablereference?view=net-9.0#system-span-1-getpinnablereference)|Returns a reference to an object of type T that can be used for pinning.<br><br>This method is intended to support .NET compilers and is not intended to be called by user code.|
|[Slice(Int32, Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.slice?view=net-9.0#system-span-1-slice(system-int32-system-int32))|Forms a slice out of the current span starting at a specified index for a specified length.|
|[Slice(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.slice?view=net-9.0#system-span-1-slice(system-int32))|Forms a slice out of the current span that begins at a specified index.|
|[ToArray()](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.toarray?view=net-9.0#system-span-1-toarray)|Copies the contents of this span into a new array.|
|[ToString()](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.tostring?view=net-9.0#system-span-1-tostring)|Returns the string representation of this [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0) object.|
|[TryCopyTo(Span<T>)](https://learn.microsoft.com/en-us/dotnet/api/system.span-1.trycopyto?view=net-9.0#system-span-1-trycopyto(system-span((-0))))|Attempts to copy the current [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0) to a destination [Span<T>](https://learn.microsoft.com/en-us/dotnet/api/system.span-1?view=net-9.0) and returns a value that indicates whether the copy operation succeeded.|

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
