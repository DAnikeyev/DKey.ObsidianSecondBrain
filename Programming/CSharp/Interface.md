---
date_added: 2025-01-23
tags:
  - csharp
sr-due: 2025-04-04
sr-interval: 3
sr-ease: 259
---
Up: [Reference Type](Reference%20Type.md)
___
 An interface provides a contract. Any [Class](Class.md), [Record](Record.md) or [Struct](Struct.md) that implements an interface must provide implementations for all the members of the interface. An interface may define static member or default implementation.
 
 Beginning with C# 11, an interface may define `static abstract` or `static virtual` members to declare that an implementing type must provide the declared members. Typically, `static virtual` methods declare that an implementation must define a set of overloaded methods.

Unlike [Abstract class](Abstract%20class.md) Interaces can't have [Constructor](Constructor.md) or non-static [[Field]]
## Content
- [Constant](Constant.md)
- [Operator](CSharp%20Operator.md)
- [static](static.md) [Constructor](Constructor.md)
- [Method](Method.md)
- [Property](Property.md)
- [[Nested types]]
- [CSharp Indexer](CSharp%20Indexer.md)
- [[Event]]
## Example
```cs
using System;

public interface IExtendedInterface
{
    // 1. Constant (non-modifiable, accessible everywhere).
    const int MyConstant = 42;

    // 2. Static field (common data shared by all implementers).
    static int MyStaticField = 10;

    // 3. Static property (similar to a static field, but with optional logic).
    static int MyStaticProperty { get; set; } = 5;

    // 4. Nested type (class, struct, or interface declared inside this interface).
    public class NestedClass
    {
        public void DisplayMessage() => Console.WriteLine("Hello from NestedClass!");
    }

    // 5. Static constructor (runs once to initialize static members).
    static IExtendedInterface()
    {
        MyStaticField = 20;
        Console.WriteLine("Static constructor in IExtendedInterface called.");
    }

    // 6. Operator overload (C# 11+ allows static operator methods in interfaces).
    static IExtendedInterface operator +(IExtendedInterface left, IExtendedInterface right)
    {
        // Implementation could combine data from left and right.
        // For simplicity, just return left.
        return left;
    }

    // 7. Non-static property with default implementation (C# 8+).
    //    If an implementing class/struct doesn't override it, this default is used.
    int DefaultProperty
    {
        get => 100; 
    }

    // 8. Abstract-like property (no default implementation).
    //    Implementers must define a body when they implement this interface.
    int RequiredProperty { get; set; }

    // 9. Static method (accessible from the interface itself).
    static void MyStaticMethod()
    {
        Console.WriteLine("Static method in IExtendedInterface called.");
    }

    // 10. Default-implemented instance method.
    void MyDefaultMethod()
    {
        Console.WriteLine("Default method implementation in IExtendedInterface.");
    }

    // 11. Indexer with a default implementation.
    int this[int index]
    {
        get => index * 2;
        set => Console.WriteLine($"Indexer set called with index {index}, value {value}.");
    }

    // 12. Event with default add/remove logic.
    event EventHandler MyEvent
    {
        add => Console.WriteLine("MyEvent added.");
        remove => Console.WriteLine("MyEvent removed.");
    }
}
```

• In C# 11, interfaces support static abstract (or static virtual) members, letting you define methods or operators that must be implemented by any type that implements the interface.  
• By declaring a static abstract operator, you ensure that each concrete implementing type provides its own version of that operator. This is particularly useful for generic math or operator overloading scenarios.
```cs
// IMyNumber.cs
public interface IMyNumber<T> where T : IMyNumber<T>
{
    // Static abstract operator member (C# 11+).
    static abstract T operator +(T left, T right);
}

// MyNumber.cs
public struct MyNumber : IMyNumber<MyNumber>
{
    private readonly int value;

    public MyNumber(int value)
    {
        this.value = value;
    }

    // Implementation of the static abstract operator from IMyNumber.
    public static MyNumber operator +(MyNumber left, MyNumber right)
    {
        return new MyNumber(left.value + right.value);
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
