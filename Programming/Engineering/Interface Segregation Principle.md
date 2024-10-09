---
date_added: 2024-10-09
tags:
  - design
  - csharp
---
Up: [SOLID principles](SOLID%20principles.md)
___
No client should be forced to implement [Interface](Interface) it does not use.
# Example
```C#
// Segregated interfaces
public interface IWorkable
{
    void Work();
}

public interface IFeedable
{
    void Eat();
}

// Class for human workers, which can work and eat
public class HumanWorker : IWorkable, IFeedable
{
    public void Work()
    {
        Console.WriteLine("Human is working.");
    }

    public void Eat()
    {
        Console.WriteLine("Human is eating.");
    }
}

// Class for robot workers, which only work
public class RobotWorker : IWorkable
{
    public void Work()
    {
        Console.WriteLine("Robot is working.");
    }
}

// Example usage
class Program
{
    static void Main()
    {
        IWorkable humanWorker = new HumanWorker();
        humanWorker.Work();

        IFeedable humanEater = new HumanWorker();
        humanEater.Eat();

        IWorkable robotWorker = new RobotWorker();
        robotWorker.Work();  // No need for Eat() for robots, adhering to ISP.
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
