---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [System.IO](System.IO.md)
___
 ```cs
 public abstract class Stream : MarshalByRefObject, IAsyncDisposable, IDisposable
```

Stream is the abstract base class of all streams. A stream is an abstraction of a sequence of bytes, such as a file, an input/output device, an inter-process communication pipe, or a TCP/IP socket
Streams involve three fundamental operations:

- You can read from streams. Reading is the transfer of data from a stream into a data structure, such as an array of bytes.
    
- You can write to streams. Writing is the transfer of data from a data structure into a stream.
    
- Streams can support seeking. Seeking refers to querying and modifying the current position within a stream.

Implements [IDisposable](IDisposable.md) interface. Disposing essentially calls the `Flush` method for you, also releases operating system resources such as file handles, network connections, or memory used for any internal buffering



## Fields

| [Null](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream.null?view=net-9.0#system-io-stream-null) | A `Stream` with no backing store. |
| ------------------------------------------------------------------------------------------------------------- | --------------------------------- |
## Properties

| [CanRead](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream.canread?view=net-9.0#system-io-stream-canread)                | When overridden in a derived class, gets a value indicating whether the current stream supports reading.            |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| [CanSeek](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream.canseek?view=net-9.0#system-io-stream-canseek)                | When overridden in a derived class, gets a value indicating whether the current stream supports seeking.            |
| [CanTimeout](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream.cantimeout?view=net-9.0#system-io-stream-cantimeout)       | Gets a value that determines whether the current stream can time out.                                               |
| [CanWrite](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream.canwrite?view=net-9.0#system-io-stream-canwrite)             | When overridden in a derived class, gets a value indicating whether the current stream supports writing.            |
| [Length](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream.length?view=net-9.0#system-io-stream-length)                   | When overridden in a derived class, gets the length in bytes of the stream.                                         |
| [Position](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream.position?view=net-9.0#system-io-stream-position)             | When overridden in a derived class, gets or sets the position within the current stream.                            |
| [ReadTimeout](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream.readtimeout?view=net-9.0#system-io-stream-readtimeout)    | Gets or sets a value, in milliseconds, that determines how long the stream will attempt to read before timing out.  |
| [WriteTimeout](https://learn.microsoft.com/en-us/dotnet/api/system.io.stream.writetimeout?view=net-9.0#system-io-stream-writetimeout) | Gets or sets a value, in milliseconds, that determines how long the stream will attempt to write before timing out. |

## Methods

1. **Read Methods:**

C#

```cs
// Synchronous read
public virtual int Read(byte[] buffer, int offset, int count)
// Asynchronous read
public virtual Task<int> ReadAsync(byte[] buffer, int offset, int count)
// Single byte read
public virtual int ReadByte()
```

1. **Write Methods:**

C#

```cs
// Synchronous write
public virtual void Write(byte[] buffer, int offset, int count)
// Asynchronous write
public virtual Task WriteAsync(byte[] buffer, int offset, int count)
// Single byte write
public virtual void WriteByte(byte value)
```

1. **Position Control Methods:**

C#

```cs
// Sets the position within the stream
public virtual long Seek(long offset, SeekOrigin origin)
// Sets the length of the stream
public virtual void SetLength(long value)
// Flushes buffers to underlying storage
public virtual void Flush()
```


 ```csharp
 using (FileStream stream = new FileStream("example.txt", FileMode.OpenOrCreate))
{
    // 1. Seek from the beginning (SeekOrigin.Begin)
    stream.Seek(10, SeekOrigin.Begin);    // Moves to 10th byte from start
    
    // 2. Seek from current position (SeekOrigin.Current)
    stream.Seek(5, SeekOrigin.Current);   // Moves 5 bytes forward from current position
    stream.Seek(-5, SeekOrigin.Current);  // Moves 5 bytes backward from current position
    
    // 3. Seek from end (SeekOrigin.End)
    stream.Seek(-20, SeekOrigin.End);     // Moves to 20th byte from end
}
 ```
1. **Key Properties:**

C#

```cs
public abstract bool CanRead { get; }
public abstract bool CanWrite { get; }
public abstract bool CanSeek { get; }
public abstract long Length { get; }
public abstract long Position { get; set; }
```

1. **Resource Management Methods:**

C#

```cs
// Implements IDisposable
public virtual void Dispose()
// Called by Dispose to release [unmanaged](Unmanaged.md) resources
protected virtual void Dispose(bool disposing)
```

## Example
 ```csharp
 using System;
using System.Threading.Tasks;
using System.Windows;
using System.IO;

namespace WpfApplication
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void Button_Click(object sender, RoutedEventArgs e)
        {
            string StartDirectory = @"c:\Users\exampleuser\start";
            string EndDirectory = @"c:\Users\exampleuser\end";

            foreach (string filename in Directory.EnumerateFiles(StartDirectory))
            {
                using (FileStream SourceStream = File.Open(filename, FileMode.Open))
                {
                    using (FileStream DestinationStream = File.Create(EndDirectory + filename.Substring(filename.LastIndexOf('\\'))))
                    {
                        await SourceStream.CopyToAsync(DestinationStream);
                    }
                }
            }
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
