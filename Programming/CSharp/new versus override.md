---
date_added: 2025-05-19
tags:
  - csharp
---
Up: [override](override.md)
___
 You can use new instead of override, but calling method from base class variable will call initial method.
 
 Consider the following class hierarchy:
 ```csharp
 public class BaseClass
{
	public virtual void Foo() { Console.WriteLine ("BaseClass.Foo"); }
}

public class Overrider : BaseClass
{
	public override void Foo() { Console.WriteLine ("Overrider.Foo"); }
}

public class Hider : BaseClass
{
	public new void Foo() { Console.WriteLine ("Hider.Foo"); }
}
 ```
 
```cs
Overrider over = new Overrider();
BaseClass b1 = over;
over.Foo(); // Overrider.Foo
b1.Foo(); // Overrider.Foo

Hider h = new Hider();
BaseClass b2 = h;
h.Foo(); // Hider.Foo
b2.Foo(); // BaseClass.Foo
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
