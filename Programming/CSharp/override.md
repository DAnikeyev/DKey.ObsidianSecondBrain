---
date_added: 2025-04-01
tags:
  - cs
---
Up: [virtual](virtual.md) [abstract](abstract.md) [Class](Class.md) [keyword](keyword.md)
___
 The `override` keyword in C# is a fundamental feature of the language that supports object-oriented programming through polymorphism. 
### Requirements for Overriding

- The method being overridden in the base class must be declared with the `virtual`, `abstract`, or `override` modifier
- The overriding method must have the same signature (name, return type, parameter types) as the base method
- The overriding method must not have a different access modifier (less accessible than the base method)
```cs
public class Base
{
    public virtual int Foo(int x) 
    { 
        return x + 1;
    }
}

public class Derived : Base
{
    public override int Foo(int x)
    {
        return x + 42; // New implementation
    }
}
```

You can prevent further overriding by using the [sealed](sealed.md) modifier:
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
