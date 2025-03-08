---
date_added: 2025-03-08
tags:
  - csharp
---
Up: [Serialization](Data/Serialization.md)
___
IFormatter Interface in C# is part of the `System.Runtime.Serialization` namespace and is used to define the basic functionality required for a formatter. A formatter is responsible for serializing and deserializing objects, which means converting an object to a format that can be easily stored or transmitted and then reconstructing the object from that format.

The `IFormatter` interface provides the following key members:

1. **Methods:**
    
    - `Serialize(Stream serializationStream, object graph)`: This method is responsible for serializing an object, or a graph of connected objects, to the provided stream. The `serializationStream` is where the serialized data will be written, and `graph` is the root object of the graph to serialize.
    - `Deserialize(Stream serializationStream)`: This method is responsible for deserializing data from the provided stream and reconstructing the object graph. The `serializationStream` contains the serialized data.
2. **Properties:**
    
    - `SerializationBinder`: This property gets or sets the `SerializationBinder` that performs type lookups during deserialization. It helps in resolving types during the deserialization process.
    - `StreamingContext`: This property gets or sets the `StreamingContext` used for serialization and deserialization. It provides contextual information about the source or destination of the serialized stream.
    - `SurrogateSelector`: This property gets or sets the `ISurrogateSelector` used to select a surrogate for a particular type during serialization and deserialization. Surrogates can be used to customize the serialization process for specific types.
```cs
using System;
using System.IO;
using System.Runtime.Serialization;
using System.Runtime.Serialization.Formatters.Binary;

// Define a simple class to serialize
[Serializable]
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
}

// Custom SerializationBinder
public class CustomSerializationBinder : SerializationBinder
{
    public override Type BindToType(string assemblyName, string typeName)
    {
        // For demonstration, let's assume the type name has changed
        if (typeName == "OldNamespace.OldPerson")
        {
            return typeof(Person);
        }

        // Default behavior
        return Type.GetType($"{typeName}, {assemblyName}");
    }
}

class Program
{
    static void Main()
    {
        // Create an instance of the object to serialize
        Person person = new Person { Name = "John Doe", Age = 30 };

        // Serialize the object
        IFormatter formatter = new BinaryFormatter();
        using (Stream stream = new FileStream("person.bin", FileMode.Create, FileAccess.Write, FileShare.None))
        {
            formatter.Serialize(stream, person);
        }

        // Deserialize the object with a custom binder
        using (Stream stream = new FileStream("person.bin", FileMode.Open, FileAccess.Read, FileShare.Read))
        {
            formatter.Binder = new CustomSerializationBinder();
            Person deserializedPerson = (Person)formatter.Deserialize(stream);
            Console.WriteLine($"Name: {deserializedPerson.Name}, Age: {deserializedPerson.Age}");
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
