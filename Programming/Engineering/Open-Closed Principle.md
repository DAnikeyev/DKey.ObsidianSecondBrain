---
date_added: 2024-10-09
tags:
  - design
  - csharp
---
Up: [SOLID principles](SOLID%20principles.md)
___
Open-Closed Principle (OCP) states that a software artifact (classes, functions, Modules) should be open for extension but closed for modification. This means that a class should be easily extendable without modifying the class itself. 

# Using [[Interface]] or [[Abstract class]]
```C#
class Cook
{
    public void PrepareFood(IFood food)
    {
        food.Cook();
    }
}
```
Different types of food can be added without modifying the Cook class.

# Using [[template method pattern]]
```C
abstract class Food
{
    public void PrepareFood()
    {
        PrepareIngredients();
        Cook();
        Serve();
    }

    protected abstract void PrepareIngredients();
    protected abstract void Cook();
    protected abstract void Serve();
}

class Pizza : Food
{
    protected override void PrepareIngredients()
    {
        Console.WriteLine("Preparing Pizza Ingredients");
    }

    protected override void Cook()
    {
        Console.WriteLine("Cooking Pizza");
    }

    protected override void Serve()
    {
        Console.WriteLine("Serving Pizza");
    }
}
```

# Using [[Strategy pattern]]
```C#
public interface ICookingStrategy
{
    void Cook();
}

public class BakeStrategy : ICookingStrategy
{
    public void Cook()
    {
        Console.WriteLine("Baking food...");
    }
}

public class GrillStrategy : ICookingStrategy
{
    public void Cook()
    {
        Console.WriteLine("Grilling food...");
    }
}

public class Cook
{
    private ICookingStrategy _cookingStrategy;

    public Cook(ICookingStrategy cookingStrategy)
    {
        _cookingStrategy = cookingStrategy;
    }

    public void PrepareFood()
    {
        _cookingStrategy.Cook();
    }
}


```

# Using [[Decorator pattern]] and [[Inheritance]]
```C#
public interface IFood
{
    void Cook();
}

public class Pizza : IFood
{
    public void Cook()
    {
        Console.WriteLine("Cooking pizza...");
    }
}

public class FoodDecorator : IFood
{
    private IFood _food;

    public FoodDecorator(IFood food)
    {
        _food = food;
    }

    public virtual void Cook()
    {
        _food.Cook();
    }
}

public class ExtraCheeseDecorator : FoodDecorator
{
    public ExtraCheeseDecorator(IFood food) : base(food) {}

    public override void Cook()
    {
        base.Cook();
        AddExtraCheese();
    }

    private void AddExtraCheese()
    {
        Console.WriteLine("Adding extra cheese");
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
