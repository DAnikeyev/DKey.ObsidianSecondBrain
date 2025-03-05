---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [Serialization](CSharp/Serialization.md)
___
Consider using one of the following alternatives:

```cs
using System.Text.Json;  
using Newtonsoft.Json;  
using ProtoBuf;  
using System.Xml.Serialization;  
using MessagePack;  
using JsonSerializer = System.Text.Json.JsonSerializer;  
  
namespace Examples;  
  
[ProtoContract]  
[MessagePackObject]  
public class Person  
{  
    [ProtoMember(1)]  
    [Key(0)]  
    public string Name { get; set; }  
  
    [ProtoMember(2)]  
    [Key(1)]  
    public int Age { get; set; }  
  
    public void Print()  
    {        Console.WriteLine($"Name: {Name}, Age: {Age}");  
    }}  
  
public class Serialization  
{  
    public void Run()  
    {        var person = new Person { Name = "Tom", Age = 23 };  
  
        // System.Text.Json  
        var data = SystemJsonSerialize(person);  
        var person0 = SystemJsonDeserialize(data);  
        person0.Print();  
  
        // Newtonsoft.Json  
        var data1 = NewtonsoftJsonSerialize(person);  
        var person1 = NewtonsoftJsonDeserialize(data1);  
        person1.Print();  
  
        // Protobuf  
        var data2 = ProtobufSerialize(person);  
        var person2 = ProtobufDeserialize(data2);  
        person2.Print();  
  
        // XmlSerializer  
        var data3 = XmlSerialize(person);  
        var person3 = XmlDeserialize(data3);  
        person3.Print();  
  
        // MessagePack  
        var data4 = MessagePackSerialize(person);  
        var person5 = MessagePackDeserialize(data4);  
        person5.Print();  
    }  
    private string SystemJsonSerialize(Person person)  
    {        return JsonSerializer.Serialize(person);  
    }  
    private Person SystemJsonDeserialize(string json)  
    {        return JsonSerializer.Deserialize<Person>(json)!;  
    }  
    private string NewtonsoftJsonSerialize(Person person)  
    {        return JsonConvert.SerializeObject(person);  
    }  
    private Person NewtonsoftJsonDeserialize(string json)  
    {        return JsonConvert.DeserializeObject<Person>(json)!;  
    }  
    private byte[] ProtobufSerialize(Person person)  
    {        using var stream = new MemoryStream();  
        Serializer.Serialize(stream, person);  
        return stream.ToArray();  
    }  
    private Person ProtobufDeserialize(byte[] data)  
    {        using var stream = new MemoryStream(data);  
        return Serializer.Deserialize<Person>(stream);  
    }  
    private string XmlSerialize(Person person)  
    {        var serializer = new XmlSerializer(typeof(Person));  
        using var stringWriter = new StringWriter();  
        serializer.Serialize(stringWriter, person);  
        return stringWriter.ToString();  
    }  
    private Person XmlDeserialize(string xml)  
    {        var serializer = new XmlSerializer(typeof(Person));  
        using var stringReader = new StringReader(xml);  
        return (Person)serializer.Deserialize(stringReader)!;  
    }  
    private byte[] MessagePackSerialize(Person person)  
    {        return MessagePackSerializer.Serialize(person);  
    }  
    private Person MessagePackDeserialize(byte[] data)  
    {        return MessagePackSerializer.Deserialize<Person>(data);  
    }}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
