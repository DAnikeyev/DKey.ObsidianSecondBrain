---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [ISerializable](ISerializable.md)
___
## Methods

 - AddValue(string, value) - Add value by name.
 - `Get[int|string...]`(string) - Get value by name.
 - 
```cs
using System;
using System.Runtime.Serialization;

[Serializable]
public class Person : ISerializable
{
    public string FirstName { get; set; }
    public string LastName { get; set; }
    public int Age { get; set; }

    // Default constructor
    public Person() { }

    // Constructor for deserialization
    protected Person(SerializationInfo info, StreamingContext context)
    {
        // Retrieve the values from SerializationInfo
        FirstName = info.GetString("FirstName");
        LastName = info.GetString("LastName");
        Age = info.GetInt32("Age");
    }

    // Method to serialize the object
    public void GetObjectData(SerializationInfo info, StreamingContext context)
    {
        // Add values to SerializationInfo
        info.AddValue("FirstName", FirstName);
        info.AddValue("LastName", LastName);
        info.AddValue("Age", Age);
    }

    public override string ToString()
    {
        return $"{FirstName} {LastName}, Age: {Age}";
    }
}

class Program
{
    static void Main()
    {
        // Create a new Person object
        Person person = new Person
        {
            FirstName = "John",
            LastName = "Doe",
            Age = 30
        };

        // Serialize the object to a memory stream
        var formatter = new System.Runtime.Serialization.Formatters.Binary.BinaryFormatter();
        using (var stream = new System.IO.MemoryStream())
        {
            formatter.Serialize(stream, person);

            // Reset the stream position to the beginning
            stream.Position = 0;

            // Deserialize the object from the memory stream
            Person deserializedPerson = (Person)formatter.Deserialize(stream);

            // Display the deserialized object
            Console.WriteLine(deserializedPerson);
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
