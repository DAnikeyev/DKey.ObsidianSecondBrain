---
date_added: 2025-01-13
tags:
  - csharp
---
Up: [[Class]]
___
 Is a syntax to create an instance of a class:
 
 ```csharp
 public class Container
{
    private int _capacity;

    public Container(int capacity) => _capacity = capacity;
}
 ```

[[Primary constructors]] are available in C# 12:
```cs
public class NamedItem(string name)
{
    public string Name => name;
}
```

You can call constructors from other constructors:
```cs
class Car
{
	private string _description;
	private uint _nWheels;
	public Car(string description, uint nWheels)
	{
		_description = description;
			_nWheels = nWheels;
	}
	public Car(string description): this(description, 4)
	{
		//Happen after the first constructor.
	}
// ...
```

### Static Constructors

Static constructors are called once per class, not per instance. They are called before the class is accessed first time and are thread-safe.
The only modifiers allowed by static constructors are unsafe and extern.
>[!Error]
> If a static constructor throws an unhandled exception, that type becomes unusable for the life of the application.
### Implicit parameterless constructors
For classes, the C# compiler automatically generates a parameterless public constructor
if and only if you do not define any constructors. However, as soon as
you define at least one constructor, the parameterless constructor is no longer
automatically generated.

### Order for subclasses:

1. From subclass to base class:
   a. Fields are initialized.
   b. Arguments to base-class constructor calls are evaluated.
2. From base class to subclass:
   a. Constructor bodies execute.

For example:

```csharp
public class B
{
    int x = 1; // Executes 3rd
    public B (int x)
    {
        ... // Executes 4th
    }
}

public class D : B
{
    int y = 1; // Executes 1st
    public D (int x)
        : base (x + 1) // Executes 2nd
    {
        ... // Executes 5th
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
