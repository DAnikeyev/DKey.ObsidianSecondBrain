---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Declaration Statement](Declaration%20Statement.md)
___
scoped keyword ensures that method can't escape the method.
 
 ```cs
 using System;

ref struct MyRefStruct
{
    public int Value;
}

class Example
{
    public void Process()
    {
        MyRefStruct myStruct = new MyRefStruct { Value = 10 };

        // Passing a scoped reference to a method
        UseScopedRef(scoped ref myStruct);

        Console.WriteLine(myStruct.Value); // Output: 20
    }

    // The scoped modifier ensures that the reference does not escape the method
    void UseScopedRef(scoped ref MyRefStruct myRef)
    {
        // Modify the value
        myRef.Value += 10;

        // The reference cannot be returned or assigned to a field
        // This would cause a compile-time error:
        // return ref myRef;
    }
}

class Program
{
    static void Main()
    {
        Example example = new Example();
        example.Process();
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
