---
date_added: 2025-01-13
tags:
  - csharp
---
Up: [[CTS]]
___
Generics allow you to defer specification of 1 or more parameters of a class or method until it is used. 


  ```csharp
 // Declare the generic class.
public class GenericList<T>
{
    public void Add(T item) { }
}

public class ExampleClass { }

class TestGenericList
{
    static void Main()
    {
        // Create a list of type int.
        GenericList<int> list1 = new();
        list1.Add(1);

        // Create a list of type string.
        GenericList<string> list2 = new();
        list2.Add("");

        // Create a list of type ExampleClass.
        GenericList<ExampleClass> list3 = new();
        list3.Add(new ExampleClass());
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
