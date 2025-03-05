---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [Custom serialization](Custom%20serialization.md)
___
Represents actions on 4 stages of serialization.
4 methods: `OnSerializing`, `OnSerialized`, `OnDeserializing`, `OnDeserialized`.
```cs
using System;
using System.Runtime.Serialization;

[Serializable]
public class Person
{
    private string name;
    private int age;
    private DateTime lastModified;
    [NonSerialized] 
    private bool isDirty;

    public Person(string name, int age)
    {
        this.name = name;
        this.age = age;
        this.lastModified = DateTime.Now;
    }

    [OnDeserializing]
    private void OnDeserializing(StreamingContext context)
    {
        // Called before the deserialization process begins
        // Initialize any default values here
        isDirty = false;
    }

    [OnDeserialized]
    private void OnDeserialized(StreamingContext context)
    {
        // Called after the deserialization is complete
        // Perform any post-deserialization logic
        lastModified = DateTime.Now;
    }

    [OnSerializing]
    private void OnSerializing(StreamingContext context)
    {
        // Called before the serialization process begins
        // Prepare object state for serialization
        lastModified = DateTime.Now;
    }

    [OnSerialized]
    private void OnSerialized(StreamingContext context)
    {
        // Called after the serialization is complete
        // Perform any post-serialization cleanup
        isDirty = false;
    }

    public override string ToString()
    {
        return $"Name: {name}, Age: {age}, Last Modified: {lastModified}";
    }
}
```

### Using

```cs
using System;
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;

class Program
{
    static void Main()
    {
        // Create a new person
        Person person = new Person("John Doe", 30);

        // Serialize the person
        using (MemoryStream stream = new MemoryStream())
        {
            BinaryFormatter formatter = new BinaryFormatter();
            formatter.Serialize(stream, person);

            // Reset stream position for deserialization
            stream.Position = 0;

            // Deserialize back to a new person object
            Person deserializedPerson = (Person)formatter.Deserialize(stream);
            
            Console.WriteLine(deserializedPerson.ToString());
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
