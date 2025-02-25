---
date_added: 2025-02-19
tags:
  - csharp
---
Up: [Collection Interface](Collection%20Interface.md)
___
 This interface is implemented by types whose values can be equated
## Usage 
Used in [Dictionary](Dictionary.md), [List](List.md) [LinkedList](LinkedList.md) when testing for equality in such methods as `Contains`, `IndexOf`, `LastIndexOf`, and `Remove`.

>[!Info]
> If you implement [IEquatable<\T>](https://learn.microsoft.com/en-us/dotnet/api/system.iequatable-1?view=net-9.0), you should also override the base class implementations of [Equals(Object)](https://learn.microsoft.com/en-us/dotnet/api/system.object.equals?view=net-9.0#system-object-equals\(system-object\)) and [GetHashCode()](https://learn.microsoft.com/en-us/dotnet/api/system.object.gethashcode?view=net-9.0#system-object-gethashcode) so that their behavior is consistent with that of the [Equals(T)](https://learn.microsoft.com/en-us/dotnet/api/system.iequatable-1.equals?view=net-9.0#system-iequatable-1-equals\(-0\)) method.
## Methods

|   |   |
|---|---|
|[Equals(T)](https://learn.microsoft.com/en-us/dotnet/api/system.iequatable-1.equals?view=net-9.0#system-iequatable-1-equals\(-0\))|Indicates whether the current object is equal to another object of the same type.|

## Example
```cs
public class ProductA : IEquatable<ProductA>
{
    public string Name { get; set; }
    public int Code { get; set; }

    public bool Equals(ProductA other)
    {
        if (other is null)
            return false;

        return this.Name == other.Name && this.Code == other.Code;
    }

    public override bool Equals(object obj) => Equals(obj as ProductA);
    public override int GetHashCode() => (Name, Code).GetHashCode();
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
