---
date_added: 2025-03-09
tags:
  - csharp
---
Up: [Working with XML](Working%20with%20XML.md)
___
System.Xml.Linq has classes like XDocument and XElement. They have more convenient methods compared to  [XMLDocument](XMLDocument.md)

| Class                    | Description                                                                                                        | Popular Methods/Properties                                                |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| `XDocument`              | Represents an entire XML document. It can contain an XML declaration, processing instructions, and a root element. | `Load()`, `Save()`, `Root`, `Declaration`, `Add()`                        |
| `XElement`               | Represents an XML element. It can contain attributes, other elements, or text.                                     | `Add()`, `Attribute()`, `Elements()`, `Value`, `SetElementValue()`        |
| `XAttribute`             | Represents an attribute of an XML element.                                                                         | `Name`, `Value`, `SetValue()`                                             |
| `XNode`                  | Represents the abstract concept of a node in the XML tree. Base class for `XElement`, `XComment`, etc.             | `NextNode`, `PreviousNode`, `Remove()`                                    |
| `XText`                  | Represents the text content of an element or attribute.                                                            | `Value`                                                                   |
| `XComment`               | Represents a comment in the XML document.                                                                          | `Value`                                                                   |
| `XDeclaration`           | Represents the XML declaration, which can include version, encoding, and standalone status.                        | `Version`, `Encoding`, `Standalone`                                       |
| `XProcessingInstruction` | Represents a processing instruction, which is used to pass information to applications.                            | `Target`, `Data`                                                          |
| `XDocumentType`          | Represents the document type definition (DTD) for an XML document.                                                 | `Name`, `PublicId`, `SystemId`, `InternalSubset`                          |
| `XNamespace`             | Represents an XML namespace.                                                                                       | `NamespaceName`, `GetName()`, `+` operator for combining with local names |
## Examples

### Modifying
```cs
using System;
using System.Xml.Linq;

class ModifyXmlExample
{
    static void Main()
    {
        // Load the XML document
        XDocument doc = XDocument.Load("library.xml");
        
        // 1. Add a new book
        XElement newBook = new XElement("book",
            new XAttribute("id", "3"),
            new XElement("title", "Advanced C# 12 Features"),
            new XElement("author", "Alice Johnson"),
            new XElement("price", 39.99)
        );
        
        doc.Root.Add(newBook);
        
        // 2. Modify an existing book
        XElement book = doc.Descendants("book")
            .FirstOrDefault(b => (string)b.Attribute("id") == "1");
            
        if (book != null)
        {
            // Update the price
            book.Element("price").Value = "34.99";
            
            // Add a publication date
            book.Add(new XElement("published", "2023-12-15"));
        }
        
        // 3. Delete a book
        XElement bookToDelete = doc.Descendants("book")
            .FirstOrDefault(b => (string)b.Attribute("id") == "2");
            
        if (bookToDelete != null)
        {
            bookToDelete.Remove();
        }
        
        // Save the modified document
        doc.Save("library_modified.xml");
        
        Console.WriteLine("XML file modified successfully!");
        Console.WriteLine(doc.ToString());
    }
}
```
### Selecting
```cs
using System;
using System.Linq;
using System.Xml.Linq;

class LinqToXmlExample
{
    static void Main()
    {
        // Load the XML document
        XDocument doc = XDocument.Load("sample.xml");
        
        // Query the XML using LINQ
        var books = from book in doc.Descendants("book")
                    select new
                    {
                        Id = (string)book.Attribute("id"),
                        Title = (string)book.Element("title"),
                        Author = (string)book.Element("author"),
                        Price = (decimal)book.Element("price")
                    };
        
        // Display the results
        foreach (var book in books)
        {
            Console.WriteLine($"Book ID: {book.Id}");
            Console.WriteLine($"Title: {book.Title}");
            Console.WriteLine($"Author: {book.Author}");
            Console.WriteLine($"Price: ${book.Price}");
            Console.WriteLine();
        }
    }
}
```

## XContainer

Is an abstract class that represents an XML node that can contain other nodes. It is the base class for `XDocument` and `XElement`.

- **Hierarchy**: `XDocument` is at the top of the hierarchy and can contain an `XElement` as its root, while `XElement` is used to represent elements within the document.
- **Content**: `XDocument` can contain an XML declaration and multiple top-level nodes, whereas `XElement` cannot.
- **Role**: `XDocument` is used for operations involving the entire document, while `XElement` is used for operations involving specific elements.
>[!Info]
> Methods `Load` and `Parse` can be used to load XDocument or XElement from a file or a string.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
