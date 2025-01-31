---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [Selection statement](Selection%20statement.md)
___
  ```csharp
DisplayWeatherReport(15.0);  // Output: Cold.
DisplayWeatherReport(24.0);  // Output: Perfect!

void DisplayWeatherReport(double tempInCelsius)
{
    if (tempInCelsius < 20.0)
    {
        Console.WriteLine("Cold.");
    }
    else
    {
        Console.WriteLine("Perfect!");
    }
}
 ```

you also can use [Ternary Conditional Operator](Ternary%20Conditional%20Operator.md) to achieve the same result.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
