---
date_added: 2025-04-03
tags:
  - csharp
---
Up: [IEnumerable](IEnumerable.md)
___
Lets you run custom (and multiple enumerations for a type)
 ```cs
 public IEnumerable GetTheCars(bool ReturnRevesed)
 {
 // Return elements in reverse order.
if (ReturnReversed)
{
    for (int i = carArray.Length; i != 0; i--)
    {
        yield return carArray[i-1];
    }
}
else
{
    // Return elements in the order they are placed in the array.
    foreach (Car c in carArray)
    {
        yield return c;
    }
}
}
```

#### usage
```cs
foreach (Car с in carLot.GetTheCars(true))
{

}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
