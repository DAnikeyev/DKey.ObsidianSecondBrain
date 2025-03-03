---
date_added: 2025-02-03
tags:
  - data
---
Up: [Serialization](CSharp/Serialization.md)
___
 
 
 ![More Compact than JSON](Pasted%20image%2020250203125649.png)
 Example:
```csharp
public byte[] Serialize<T>(T thisObj)
{
    var serializer = MessagePackSerializer.Create<T>();

    using (var byteStream = new MemoryStream())
    {
        serializer.Pack(byteStream, thisObj);
        return byteStream.ToArray();
    }
}

public T Deserialize<T>(byte[] bytes)
{
    var serializer = MessagePackSerializer.Create<T>();
    using (var byteStream = new MemoryStream(bytes))
    {
        return serializer.Unpack(byteStream);
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
