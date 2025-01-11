---
date_added: 2025-01-11
tags:
  - design
---
Up: [Object-Oriented Programming](Object-Oriented%20Programming.md)
___
 is when calling code can be independent of which class of supported ierarchy it is operating on. The specific class is not known until runtime. This allows for a single interface to be used to represent a group of related classes. 
 
## **Why Do We Need It:**  
Polymorphism allows objects to be treated as instances of their parent class rather than their actual class. This enables flexibility and the ability to implement dynamic behavior, making the code more extensible and easier to maintain.

## **How It's Used in Practice:**  
Through method overriding (runtime polymorphism) and method overloading (compile-time polymorphism), developers can write code that works with objects of different types in a uniform way.

```C#
// Base class
public abstract class Animal
{
    public abstract void MakeSound();
}

// Derived class 1
public class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Bark!");
    }
}

// Derived class 2
public class Cat : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Meow!");
    }
}

// Usage
public class Program
{
    public static void Main()
    {
        List<Animal> animals = new List<Animal>
        {
            new Dog(),
            new Cat()
        };

        foreach (var animal in animals)
        {
            animal.MakeSound(); // Outputs "Bark!" and "Meow!" respectively
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
