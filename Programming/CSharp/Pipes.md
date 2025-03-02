---
date_added: 2025-02-28
tags:
  - csharp
---
Up: [System.IO](System.IO.md)
___
 Contains types that provide a means for interprocess communication through anonymous and/or named pipes.

## Example
Client
 ```csharp
 using System.IO;
using System.IO.Pipes;

public void SendImage(string filePath)
{
    using (var pipeClient = new NamedPipeClientStream(".", "ImagePipe", PipeDirection.Out))
    {
        pipeClient.Connect();
        byte[] imageBytes = File.ReadAllBytes(filePath);
        pipeClient.Write(imageBytes, 0, imageBytes.Length);
    }
}
 ```

Server
```cs
using System.IO;
using System.IO.Pipes;

public void ReceiveImage()
{
    using (var pipeServer = new NamedPipeServerStream("ImagePipe", PipeDirection.In))
    {
        pipeServer.WaitForConnection();
        using (var memoryStream = new MemoryStream())
        {
            pipeServer.CopyTo(memoryStream);
            byte[] imageBytes = memoryStream.ToArray();
            // Process the image bytes, e.g., save to disk or display in a web form
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
