---
date_added: 2025-02-03
tags:
  - csharp
---
Up: [Serialization](Data/Serialization.md)
___
System.Text.Json is a high-performance JSON framework o serialize and deserialize JSON data.

>[!Info]
> Do not confuse with [Iserializable interface](https://learn.microsoft.com/en-us/dotnet/api/system.runtime.serialization.iserializable?view=net-9.0)

## Basic Requirements for Serializable Objects:

- Objects must have a public parameterless constructor (default constructor)
- Properties must have public get and set accessors
- Fields are not serialized by default (only properties are)

## [Attribute](Attribute.md) for Serialization:

 ```csharp
 using System.Text.Json.Serialization;

public class Person
{
    [JsonPropertyName("full_name")]  // Customize the JSON property name
    public string Name { get; set; }
    
    [JsonIgnore]  // Exclude property from serialization
    public int InternalId { get; set; }
    
    [JsonInclude]  // Include a field in serialization
    private readonly string _privateField;
}
 ```

## Serialization options

 ```csharp
 var options = new JsonSerializerOptions
{
    WriteIndented = true,  // Pretty print JSON
    PropertyNameCaseInsensitive = true,  // Case-insensitive property matching
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase,  // Camel case property names
};

string json = JsonSerializer.Serialize(person, options);
Person deserialized = JsonSerializer.Deserialize<Person>(json, options);var options = new JsonSerializerOptions
{
    WriteIndented = true,  // Pretty print JSON
    PropertyNameCaseInsensitive = true,  // Case-insensitive property matching
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase,  // Camel case property names
};

string json = JsonSerializer.Serialize(person, options);
Person deserialized = JsonSerializer.Deserialize<Person>(json, options);
 ```
## **Best Practices**:
1. Always use properties instead of fields for serialization
2. Consider using attributes to control serialization behavior
3. Use strong typing with `Deserialize<T>` instead of dynamic deserialization
4. Handle potential exceptions during serialization/deserialization
5. Use custom options when default behavior doesn't meet your needs
## Constructor
**[JsonConstructor]**: Specifies that the constructor is used during deserialization
 ```csharp
 public class Person
{
    public string Name { get; }
    public int Age { get; }

    [JsonConstructor]
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}
 ```
## References
 1. [JSON](JSON.md)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
