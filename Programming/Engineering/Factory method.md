---
date_added: 2025-02-03
tags:
  - design
---
Up: [Creational pattern](Creational%20pattern.md)]
___
 is a creational design pattern that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.
 ![](Pasted%20image%2020250203190738.png)

## Example 
```cs
// Step 1: Create an interface (or abstract class) for the product
public interface IVehicle
{
    void Drive();
}

// Step 2: Create concrete products
public class Car : IVehicle
{
    public void Drive()
    {
        Console.WriteLine("Driving a car...");
    }
}

public class Motorcycle : IVehicle
{
    public void Drive()
    {
        Console.WriteLine("Riding a motorcycle...");
    }
}

public class Truck : IVehicle
{
    public void Drive()
    {
        Console.WriteLine("Driving a truck...");
    }
}

// Step 3: Create the Factory class
public class VehicleFactory
{
    public IVehicle CreateVehicle(string vehicleType)
    {
        switch (vehicleType.ToLower())
        {
            case "car":
                return new Car();
            case "motorcycle":
                return new Motorcycle();
            case "truck":
                return new Truck();
            default:
                throw new ArgumentException("Invalid vehicle type");
        }
    }
}

// Step 4: Usage example
public class Program
{
    public static void Main()
    {
        VehicleFactory factory = new VehicleFactory();

        // Create different types of vehicles using the factory
        IVehicle car = factory.CreateVehicle("car");
        IVehicle motorcycle = factory.CreateVehicle("motorcycle");
        IVehicle truck = factory.CreateVehicle("truck");

        // Use the vehicles
        car.Drive();        // Output: Driving a car...
        motorcycle.Drive(); // Output: Riding a motorcycle...
        truck.Drive();      // Output: Driving a truck...
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
