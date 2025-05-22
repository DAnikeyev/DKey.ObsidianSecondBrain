---
date_added: 2025-05-19
tags:
  - csharp
---
Up: [Fundamental Interfaces](Fundamental%20Interfaces.md)
___
 The System.Numerics.INumber\<TSelf> interface (new to .NET 7) unifies arithmetic
operations across all numeric types, allowing generic methods such as the
following to be written:
```cs
T Sum<T> (T[] numbers) where T : INumber<T>
{
	T total = T.Zero;
	foreach (T n in numbers)
		total += n; // Invokes addition operator for any numeric type
	return total;
}

int intSum = Sum (3, 5, 7);
double doubleSum = Sum (3.2, 5.3, 7.1);
decimal decimalSum = Sum (3.2m, 5.3m, 7.1m);
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
