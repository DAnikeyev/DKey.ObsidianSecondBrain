---
date_added: 2025-02-27
tags:
  - csharp
---
Up: [Common attributes](Common%20attributes.md)
___
 Indicates that a class can be serialized using binary or XML serialization. This class cannot be inherited.

```cs


// A test object that needs to be serialized.
[Serializable()]
public class TestSimpleObject  {

    public int member1;
    public string member2;
    public string member3;
    public double member4;

    // A field that is not serialized.
    [NonSerialized()] public string member5;

    public TestSimpleObject() {

        member1 = 11;
        member2 = "hello";
        member3 = "hello";
        member4 = 3.14159265;
        member5 = "hello world!";
    }

    public void Print() {

        Console.WriteLine("member1 = '{0}'", member1);
        Console.WriteLine("member2 = '{0}'", member2);
        Console.WriteLine("member3 = '{0}'", member3);
        Console.WriteLine("member4 = '{0}'", member4);
        Console.WriteLine("member5 = '{0}'", member5);
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
