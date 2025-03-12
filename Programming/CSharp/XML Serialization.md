---
date_added: 2025-02-03
tags:
  - csharp
---
Up: [Serialization](CSharp/Serialization.md) [Working with XML](Working%20with%20XML.md)
___
## **Required for XML Serialization:**

- Classes must have a parameterless constructor
- Properties must have both get and set accessors
- Classes and properties must be public
 ```csharp
[XmlRoot("ElementName")]      // Specify root element name
[XmlElement("ElementName")]   // Specify element name
[XmlAttribute("AttrName")]   // Serialize as attribute
[XmlIgnore]                  // Skip serialization
[XmlArray("ArrayName")]      // Specify array element name
[XmlArrayItem("ItemName")]   // Specify array item element name
 ```

## Example

 ```csharp
// 1. First, let's create a class we want to serialize
using System.Xml.Serialization;

// Define a class with XML attributes
[XmlRoot("Person")] // Optional: specify the root element name
public class Person
{
    // Simple property
    public string Name { get; set; }

    // Property with custom XML element name
    [XmlElement("BirthDate")]
    public DateTime DateOfBirth { get; set; }

    // Property as XML attribute
    [XmlAttribute("id")]
    public int PersonId { get; set; }

    // Ignore this property during serialization
    [XmlIgnore]
    public string TemporaryData { get; set; }

    // Array or List property
    [XmlArray("Addresses")]
    [XmlArrayItem("Address")]
    public List<Address> Addresses { get; set; }

    // IMPORTANT: XML Serializer requires parameterless constructor
    public Person()
    {
        Addresses = new List<Address>();
    }
}

public class Address
{
    public string Street { get; set; }
    public string City { get; set; }
    
    // Required for XML Serialization
    public Address() { }
}

// 2. Example usage:
public class XmlSerializationExample
{
    public void SerializeExample()
    {
        // Create test data
        var person = new Person
        {
            Name = "John Doe",
            DateOfBirth = new DateTime(1990, 1, 1),
            PersonId = 123,
            Addresses = new List<Address>
            {
                new Address { Street = "123 Main St", City = "New York" },
                new Address { Street = "456 Side St", City = "Boston" }
            }
        };

        // Create XML Serializer
        XmlSerializer serializer = new XmlSerializer(typeof(Person));

        // Serialize to file
        using (StreamWriter writer = new StreamWriter("person.xml"))
        {
            serializer.Serialize(writer, person);
        }

        // Serialize to string
        using (StringWriter stringWriter = new StringWriter())
        {
            serializer.Serialize(stringWriter, person);
            string xmlString = stringWriter.ToString();
            Console.WriteLine(xmlString);
        }

        // Deserialize from file
        using (StreamReader reader = new StreamReader("person.xml"))
        {
            Person deserializedPerson = (Person)serializer.Deserialize(reader);
            Console.WriteLine($"Deserialized name: {deserializedPerson.Name}");
        }
    }
}
 ```

### Serializing collection:
 ```csharp
 [Serializable, XmlRoot(Namespace = "http://www.MyCompany.com")]
public class JamesBondCar : Car
{
    public JamesBondCar(bool skyWorthy, bool seaworthy)
    {
        canFly = skyWorthy;
        canSubmerge = seaworthy;
    }

    // XmlSerializer requires a default constructor!
    public JamesBondCar() { selectedText }
}

static void SaveListOfCars()
{
    // Save a list of JamesBondCar objects.
    List<JamesBondCar> myCars = new List<JamesBondCar>();
    myCars.Add(new JamesBondCar(true, true));
    myCars.Add(new JamesBondCar(true, false));
    myCars.Add(new JamesBondCar(false, true));
    myCars.Add(new JamesBondCar(false, false));

    using (Stream fStream = new FileStream("CarCollection.xml",
        FileMode.Create, FileAccess.Write, FileShare.None))
    {
        XmlSerializer xmlFormat = new XmlSerializer(typeof(List<JamesBondCar>));
        xmlFormat.Serialize(fStream, myCars);
    }
    Console.WriteLine("=> Saved list of cars!");
}
 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
