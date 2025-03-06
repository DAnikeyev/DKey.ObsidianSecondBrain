---
date_added: 2025-03-06
tags:
  - csharp
---
Up: [Custom Attributes](Custom%20Attributes.md)
___

Specify attribute targets and other info
 ```cs
 using System;

// Define a custom attribute with AttributeUsage
[AttributeUsage(AttributeTargets.Class | AttributeTargets.Method, Inherited = false, AllowMultiple = true)]
public class MyCustomAttribute : Attribute
{
    public string Description { get; }

    public MyCustomAttribute(string description)
    {
        Description = description;
    }
}

// Apply the custom attribute to a class
[MyCustomAttribute("This is a sample class.")]
public class SampleClass
{
    // Apply the custom attribute to a method
    [MyCustomAttribute("This is a sample method.")]
    public void SampleMethod()
    {
        Console.WriteLine("Executing SampleMethod.");
    }
}

public class Program
{
    public static void Main()
    {
        // Retrieve and display the custom attributes applied to SampleClass
        var classAttributes = typeof(SampleClass).GetCustomAttributes(typeof(MyCustomAttribute), false);
        foreach (MyCustomAttribute attr in classAttributes)
        {
            Console.WriteLine($"Class Attribute Description: {attr.Description}");
        }

        // Retrieve and display the custom attributes applied to SampleMethod
        var methodAttributes = typeof(SampleClass).GetMethod("SampleMethod").GetCustomAttributes(typeof(MyCustomAttribute), false);
        foreach (MyCustomAttribute attr in methodAttributes)
        {
            Console.WriteLine($"Method Attribute Description: {attr.Description}");
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
