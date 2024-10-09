---
date_added: 2024-10-09
tags:
  - design
  - csharp
---
Up: [SOLID principles](SOLID%20principles.md)
___
 Let f(x) be a property provable about objects x of type T. Then f(y) should be true for objects y of type S where S is a subtype of T.  

# Example
Here Penguin violates LSP
```C#
public class Bird
{
	public virtual void Fly()
	{ 
	Console.WriteLine("The bird is flying.");
	}
}

public class Sparrow : Bird 
{
	public override void Fly() 
	{
		Console.WriteLine("The sparrow is flying.");
	}
}

public class Penguin : Bird 
{
	public override void Fly() 
	{
		throw new InvalidOperationException("Penguins can't fly.");
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
