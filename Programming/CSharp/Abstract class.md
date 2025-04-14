---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [[Class]]
___
 1. **Cannot be Instantiated:**
    
    - You cannot create an instance of an abstract class directly. It is meant to be inherited by other classes.
2. **Abstract Methods:**
    
    - An abstract class can include abstract methods, which are declared without an implementation. Derived classes must provide an implementation for these methods.
3. **Non-Abstract Methods:**
    
    - Abstract classes can also have methods with implementations. These methods can be used by derived classes without modification or can be overridden if needed.
4. **Fields and Properties:**
    
    - Abstract classes can have fields and properties, which can be used to store data and provide access to it.
5. **Constructors:**
    
    - Abstract classes can have constructors, which are called when an instance of a derived class is created.
6. **Access Modifiers:**
    
    - Abstract classes and their members can have access modifiers (e.g., public, protected) to control visibility.

### Example:

```cs
public abstract class Animal
{
    // Abstract method (no implementation)
    public abstract void MakeSound();

    // Non-abstract method (with implementation)
    public void Sleep()
    {
        Console.WriteLine("Sleeping...");
    }
}

public class Dog : Animal
{
    // Implementing the abstract method
    public override void MakeSound()
    {
        Console.WriteLine("Bark!");
    }
}

public class Cat : Animal
{
    // Implementing the abstract method
    public override void MakeSound()
    {
        Console.WriteLine("Meow!");
    }
}

public class Program
{
    public static void Main()
    {
        Animal myDog = new Dog();
        myDog.MakeSound(); // Output: Bark!
        myDog.Sleep();     // Output: Sleeping...

        Animal myCat = new Cat();
        myCat.MakeSound(); // Output: Meow!
        myCat.Sleep();     // Output: Sleeping...
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
