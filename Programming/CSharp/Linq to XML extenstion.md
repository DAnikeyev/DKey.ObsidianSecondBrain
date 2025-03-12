---
date_added: 2025-03-10
tags:
  - csharp
---
Up: [LINQ to XML](LINQ%20to%20XML.md)
___
 Extend [Generic IEnumerable](Generic%20IEnumerable.md) with constraints for example
```cs
public static System.Collections.Generic.IEnumerable<System.Xml.Linq.XElement> Ancestors<T>(this System.Collections.Generic.IEnumerable<T?> source) where T : System.Xml.Linq.XNode;
```

## Main methods

| Member             | Description                                                                                                                           |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| Ancestor<T>()      | Returns a filtered collection of elements that contains the ancestors of each node in the source collection                           |
| Attributes()       | Returns a filtered collection of attributes of each element in the source collection                                                  |
| DescendantNodes<T> | Returns a collection of descendant nodes of each document and element in the source collection                                        |
| Descendants<T>     | Returns a filtered collection of elements that contains the descendant elements of each element and document in the source collection |
| Elements<T>        | Returns a collection of child elements of each element and document in the source collection                                          |
| Nodes<T>           | Returns a collection of child nodes of each document and element in the source collection                                             |
| Remove()           | Removes each attribute in the source collection from its parent element                                                               |
| Remove<T>()        | Removes all occurrences of the specified node in the source collection                                                                |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
