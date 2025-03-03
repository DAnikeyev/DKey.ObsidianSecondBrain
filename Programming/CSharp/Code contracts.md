---
date_added: 2025-03-03
tags:
  - csharp
---
Up: [CSharp Fundamentals](CSharp%20Fundamentals.md)
___
## Preconditions:
These are conditions that must be true before a method or property is executed.
  ```csharp
 public void SomeMethod(int value)
{
    Contract.Requires(value > 0, "Value must be greater than zero.");
    // Method implementation
}
 ```

## Postconditions:
These are conditions that must be true after a method or property has finished executing.
 ```csharp
 public int Calculate(int a, int b)
{
    Contract.Ensures(Contract.Result<int>() >= 0, "Result must be non-negative.");
    return a + b;
}
 ```

## Invariants:
```cs
public class MyClass
{
    private int _value;

    [ContractInvariantMethod]
    private void ObjectInvariant()
    {
        Contract.Invariant(_value >= 0, "Value must be non-negative.");
    }
}
```

IsCalled:
- After the execution of each public method or property.
- After the execution of each constructor.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
