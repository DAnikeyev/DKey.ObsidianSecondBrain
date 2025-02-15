---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
 The `ValuesAttribute` is used to specify a set of values to be provided for an individual parameter of a parameterized test method.
 ```csharp
[Test]
public void MyTest([Values(1, 2, 3)] int x, [Values("A", "B")] string s)
{
    /* ... */
}
```

## Values with Enum or Boolean
When used without any arguments, the **[Values]** attribute on an enum parameter will automatically include all possible values of the enumeration.

```csharp
[Test]
public void MyEnumTest([Values]MyEnumType myEnumArgument)
{
    //...
}
```

There is the same support for Boolean values. Add the **[Values]** attribute to a bool and the method will be run with true and false.

```csharp
[Test]
public void MyBoolTest([Values]bool value)
{
    //...
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
