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

Primary constructors are available in C# 12:
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


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
