---
date_added: 2025-03-10
tags:
  - csharp
---
Up: [LINQ to XML](LINQ%20to%20XML.md)
___
 XStreamingElement supports deferred execution, Tree is not build (no extra memory/time is wasted) until it is used.
 
 ```cs
 XElement srcTree = new XElement("Root",
                       new XElement("Child", 1),
                       new XElement("Child", 2),
                       new XElement("Child", 3),
                       new XElement("Child", 4),
                       new XElement("Child", 5)
                   );

XElement dstTree1 = new XElement("NewRoot",
                        from el in srcTree.Elements()
                        where (int)el >= 3
                        select new XElement("DifferentChild", (int)el)
                    );

XStreamingElement dstTree2 = new XStreamingElement("NewRoot",
                        from el in srcTree.Elements()
                        where (int)el >= 3
                        select new XElement("DifferentChild", (int)el)
                    );

Console.WriteLine(dstTree1);
Console.WriteLine("------");
Console.WriteLine(dstTree2);
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
