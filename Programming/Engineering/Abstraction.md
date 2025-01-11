---
date_added: 2025-01-11
tags:
  - design
---
Up: [Object-Oriented Programming](Object-Oriented%20Programming.md)
___
 Abstraction is a process of modeling the relevant attributes and interactions of entities as classes to define an abstract representation of a system
## **Why Do We Need It:**  
Abstraction allows developers to focus on **what** an object does instead of **how** it does it. It simplifies complex systems by modeling classes appropriate to the problem, hiding unnecessary implementation details.

## **How It's Used in Practice:**  
Using abstract classes and interfaces, developers can define contracts that other classes must follow. This promotes a clear separation of concerns and makes the system easier to manage and extend.
```C#
// Abstract class defining a contract for shapes
public abstract class Shape
{
    // Abstract method: must be implemented by derived classes
    public abstract double CalculateArea();

    // Concrete method: common functionality
    public void Display()
    {
        Console.WriteLine($"Area: {CalculateArea()}");
    }
}

// Derived class implementing the abstract method
public class Circle : Shape
{
    public double Radius { get; set; }

    public Circle(double radius)
    {
        Radius = radius;
    }

    public override double CalculateArea()
    {
        return Math.PI * Radius * Radius;
    }
}

// Usage
Shape circle = new Circle(5);
circle.Display(); // Outputs: Area: 78.53981633974483
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
