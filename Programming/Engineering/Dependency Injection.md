---
date_added: 2024-10-15
tags:
  - design
---
Up: [Design pattern](Design%20pattern.md)
___

opposite of  [[Dependency Construction]]

```C#
// Dependency class
public class MyDependency
{
    public void DoWork()
    {
        Console.WriteLine("Dependency doing work...");
    }
}

// Class using the dependency
public class MyClass
{
    private readonly MyDependency _dependency;

    // Constructor Injection
    public MyClass(MyDependency dependency)
    {
        _dependency = dependency;
    }

    public void Execute()
    {
        _dependency.DoWork();
    }
}

// Usage example
class Program
{
    static void Main(string[] args)
    {
        // Dependency is created outside the class and injected
        MyDependency dependency = new MyDependency();
        MyClass myClass = new MyClass(dependency);

        myClass.Execute();
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
