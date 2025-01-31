---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Jump statement](Jump%20statement.md)
___
 
 >[!Tip]
> When you work with nested loops, consider refactoring separate loops into separate methods. That may lead to a simpler, more readable code without the `goto` statement.

`Label:`

...
`goto Label;`

## goto case

in [switch] statements can tranfer control to another case:
```cs
using System;

public enum CoffeeChoice
{
    Plain,
    WithMilk,
    WithIceCream,
}

public class GotoInSwitchExample
{
    public static void Main()
    {
        Console.WriteLine(CalculatePrice(CoffeeChoice.Plain));  // output: 10.0
        Console.WriteLine(CalculatePrice(CoffeeChoice.WithMilk));  // output: 15.0
        Console.WriteLine(CalculatePrice(CoffeeChoice.WithIceCream));  // output: 17.0
    }

    private static decimal CalculatePrice(CoffeeChoice choice)
    {
        decimal price = 0;
        switch (choice)
        {
            case CoffeeChoice.Plain:
                price += 10.0m;
                break;

            case CoffeeChoice.WithMilk:
                price += 5.0m;
                goto case CoffeeChoice.Plain;

            case CoffeeChoice.WithIceCream:
                price += 7.0m;
                goto case CoffeeChoice.Plain;
        }
        return price;
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
