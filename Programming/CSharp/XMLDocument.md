---
date_added: 2025-03-09
tags:
  - csharp
---
Up: [Working with XML](Working%20with%20XML.md)
___
Uses System.Xml namespace to work with XML documents. It provides classes to create, read, and manipulate XML documents.


```cs
  
    // Create a new XmlDocument  
    XmlDocument doc = new XmlDocument();  
  
    // Create the root element  
    XmlElement root = doc.CreateElement("Root");  
    doc.AppendChild(root);  
  
    // Create and append an element with attributes  
    XmlElement elementWithAttributes = doc.CreateElement("ElementWithAttributes");  
    elementWithAttributes.SetAttribute("Attribute1", "Value1");  
    elementWithAttributes.SetAttribute("Attribute2", "Value2");  
    root.AppendChild(elementWithAttributes);  
  
    // Create and append a comment node  
    XmlNode commentNode = doc.CreateNode(XmlNodeType.Comment, "", "");  
    commentNode.Value = "This is a comment";  
    root.AppendChild(commentNode);  
  
    // Create and append a CDATA section  
    XmlCDataSection cdataSection = doc.CreateCDataSection("This is CDATA content");  
    root.AppendChild(cdataSection);  
  
    // Create and append 5 child elements  
    for (int i = 1; i <= 5; i++)  
    {        XmlElement child = doc.CreateElement("Element" + i);  
        child.InnerText = "This is element " + i;  
        root.AppendChild(child);  
    }  
    // Save the document to a file in the AppContext.BaseDirectory  
    string filePath = System.IO.Path.Combine(AppContext.BaseDirectory, "example.xml");  
    doc.Save(filePath);
```

| Class                 | Description                                                         | Popular Methods/Properties                                           |
| --------------------- | ------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `XmlDocument`         | Represents an XML document. It is the root of the XML DOM.          | `Load()`, `Save()`, `DocumentElement`, `CreateElement()`             |
| `XmlElement`          | Represents an element in an XML document.                           | `GetAttribute()`, `SetAttribute()`, `InnerText`, `AppendChild()`     |
| `XmlNode`             | Represents a single node in the XML document.                       | `ChildNodes`, `ParentNode`, `Attributes`, `SelectSingleNode()`       |
| `XmlAttribute`        | Represents an attribute of an XML element.                          | `Name`, `Value`, `OwnerElement`                                      |
| `XmlNodeList`         | Represents an ordered collection of nodes.                          | `Count`, `Item()`, `GetEnumerator()`                                 |
| `XmlReader`           | Provides a fast, non-cached, forward-only way to read XML data.     | `Read()`, `IsStartElement()`, `ReadElementContentAsString()`         |
| `XmlWriter`           | Provides a fast, non-cached, forward-only way to generate XML data. | `WriteStartElement()`, `WriteString()`, `WriteEndElement()`          |
| `XmlTextReader`       | Provides a fast, non-cached, forward-only way to read XML data.     | `Read()`, `Name`, `Value`, `NodeType`                                |
| `XmlTextWriter`       | Provides a fast, non-cached, forward-only way to generate XML data. | `WriteStartElement()`, `WriteAttributeString()`, `WriteEndElement()` |
| `XmlNamespaceManager` | Resolves, adds, and removes namespaces to a collection.             | `AddNamespace()`, `LookupNamespace()`, `LookupPrefix()`              |

## Example 
 ```cs
 using System;
using System.Xml;

class Program
{
    static void Main()
    {
        XmlDocument doc = new XmlDocument();
        doc.Load("example.xml"); // Load the XML file

        // Access elements
        XmlNodeList elements = doc.GetElementsByTagName("elementName");
        foreach (XmlNode element in elements)
        {
            Console.WriteLine(element.InnerText);
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
