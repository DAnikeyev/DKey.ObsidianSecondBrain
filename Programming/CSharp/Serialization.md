---
date_added: 2025-02-03
tags:
  - csharp
sr-due: 2025-04-05
sr-interval: 4
sr-ease: 272
---
Up: [Other CSharp Features](Other%20CSharp%20Features.md)
___
 Serialization is the process of converting the state of an object into a form that can be persisted or transported. The complement of serialization is deserialization, which converts a [[Stream]] or a [String](String.md) into an object. Together, these processes allow data to be stored and transferred

- Use [Serializable attribute](Serializable%20attribute.md) for simple binary serialization when you don't need to customize the process.
	- Use [ISerializable](ISerializable.md) when you need to control the serialization process, such as adding custom logic or handling complex objects.
- For [XML Serialization](XML%20Serialization.md), use `XmlSerializer` and ensure your class has a parameterless constructor and public properties. The `[Serializable]` attribute is not used in this context.
## References
 1. [Serialization](Data/Serialization.md)
 2. [ISerializable](ISerializable.md)
 3. [Serializable attribute](Serializable%20attribute.md)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
