---
date_added: 2025-01-11
tags:
  - csharp
sr-due: 2025-03-28
sr-interval: 3
sr-ease: 250
---
Up: [CSharp Fundamentals](CSharp%20Fundamentals.md)
___
 Using delegates, C# allows functions to be passed as values to and from other functions.
Instance of delegate represent a method with a parameter list and return type.
```cs
public delegate int PerformCalculation(int x, int y);
```

When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.

Delegates have the following properties:

- Delegates allow methods to be passed as parameters.
- Delegates can be used to define callback methods.
- Delegates can be chained together; for example, multiple methods can be called on a single event. See [Multicast Delegates](Multicast%20Delegates.md).
- Methods don't have to match the delegate type exactly. For more information, see [Using Variance in Delegates](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates). or [Covariance and contravariance in generics](Covariance%20and%20contravariance%20in%20generics.md)
- Assignment can be done using [Delegate Operator](Delegate%20Operator.md) or [Lambda Expressions](Lambda%20Expressions.md)
- Lambda expressions are a more concise way of writing inline code blocks. Lambda expressions (in certain contexts) are compiled to delegate types. For more information about lambda expressions, see [Lambda Expressions](Lambda%20Expressions.md)





# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
