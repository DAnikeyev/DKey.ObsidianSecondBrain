---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [System.Numerics](System.Numerics.md)
___
```cs
using System;
using System.Numerics;

class Program
{
    static void Main()
    {
        // Creating BigInteger instances
        BigInteger bigInt1 = BigInteger.Parse("123456789012345678901234567890");
        BigInteger bigInt2 = BigInteger.Parse("987654321098765432109876543210");

        // Performing arithmetic operations
        BigInteger sum = bigInt1 + bigInt2;
        BigInteger difference = bigInt1 - bigInt2;
        BigInteger product = bigInt1 * bigInt2;
        BigInteger quotient = bigInt2 / bigInt1;

        // Displaying results
        Console.WriteLine($"Sum: {sum}");
        Console.WriteLine($"Difference: {difference}");
        Console.WriteLine($"Product: {product}");
        Console.WriteLine($"Quotient: {quotient}");
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
