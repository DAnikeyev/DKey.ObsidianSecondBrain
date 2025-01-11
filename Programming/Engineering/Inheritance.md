---
date_added: 2025-01-11
tags:
  - design
---
Up: [Object-Oriented Programming](Object-Oriented%20Programming.md)
___
 Ability to create new abstraction based on existing abstraction
## **Why Do We Need It:**  
Inheritance promotes code reusability by allowing new classes to inherit properties and methods from existing classes. It establishes a hierarchical relationship, making it easier to manage and extend code.

## **How It's Used in Practice:**  
Developers can create base (parent) classes with shared functionality and derive (child) classes that extend or specialize this functionality. This reduces redundancy and enhances maintainability.

```C#
// Base class
public class Vehicle
{
    public string Make { get; set; }
    public string Model { get; set; }

    public void StartEngine()
    {
        Console.WriteLine("Engine started.");
    }
}

// Derived class
public class Car : Vehicle
{
    public int NumberOfDoors { get; set; }

    public void OpenTrunk()
    {
        Console.WriteLine("Trunk opened.");
    }
}

// Usage
Car car = new Car
{
    Make = "Toyota",
    Model = "Camry",
    NumberOfDoors = 4
};

car.StartEngine();    // Inherited method
car.OpenTrunk();      // Specific method
Console.WriteLine($"{car.Make} {car.Model} with {car.NumberOfDoors} doors.");
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
