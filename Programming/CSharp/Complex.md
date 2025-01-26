---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [System.Numerics](System.Numerics.md)
___
 using System;
using System.Numerics;

class Program
{
    static void Main()
    {
        // Creating Complex numbers
        Complex complex1 = new Complex(2, 3); // 2 + 3i
        Complex complex2 = new Complex(4, -1); // 4 - i

        // Performing arithmetic operations
        Complex sum = complex1 + complex2;
        Complex difference = complex1 - complex2;
        Complex product = complex1 * complex2;
        Complex quotient = complex1 / complex2;

        // Displaying results
        Console.WriteLine($"Complex1: {complex1}");
        Console.WriteLine($"Complex2: {complex2}");
        Console.WriteLine($"Sum: {sum}");
        Console.WriteLine($"Difference: {difference}");
        Console.WriteLine($"Product: {product}");
        Console.WriteLine($"Quotient: {quotient}");

        // Additional operations
        double magnitude = complex1.Magnitude;
        double phase = complex1.Phase;

        Console.WriteLine($"Magnitude of Complex1: {magnitude}");
        Console.WriteLine($"Phase of Complex1: {phase}");
    }
}
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
