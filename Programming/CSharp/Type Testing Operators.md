---
date_added: 2025-01-21
tags:
  - csharp
---
Up: [CSharp Operator](CSharp%20Operator.md)
___

>[!Info]
> The `is`, `as`, and `typeof` operators can't be overloaded.
## Is operator
```cs
E is T
```
where E is an expression and T is a type. The is operator checks if the expression can be converted to the type.
>[!Info]
> E can't be anonymous method or lambda expression

is returns true if:
- the runtime type of E is the same as T, derived from T, implements interface T, or another [implicit reference conversion](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/conversions#1028-implicit-reference-conversions) exists from it to `T`
- `E` is  a nullable value type `T?` and E hasValue == true
- There exists [[Boxing and Unboxing|Boxing or unboxing]] conversion from E to T
Is operator doesn't consider user-defined conversions.
```cs
public class Base { }

public class Derived : Base { }

public static class IsOperatorExample
{
    public static void Main()
    {
        object b = new Base();
        Console.WriteLine(b is Base);  // output: True
        Console.WriteLine(b is Derived);  // output: False

        object d = new Derived();
        Console.WriteLine(d is Base);  // output: True
        Console.WriteLine(d is Derived); // output: True
    }
}
```

# As operator

Explicit conversion operator, that, unlike the cast operator doesn't throw an exception if the conversion is not possible. Instead, it returns null.
```cs
E as T
// Is the same as
E is T ? (T)(E) : (T)null
```

## Cast operator

- Implicit conversion operator that performs a conversion between compatible types`string s = 5;`
- Explicit conversion operator that performs a conversion between convertable types`var s = (string)value;`
## Typeof operator

Returns a `Type` object that represents the type of a specified object.
```cs
void PrintType<T>() => Console.WriteLine(typeof(T));

Console.WriteLine(typeof(List<string>));
PrintType<int>();
PrintType<System.Int32>();
PrintType<Dictionary<int, char>>();
// Output:
// System.Collections.Generic.List`1[System.String]
// System.Int32
// System.Int32
// System.Collections.Generic.Dictionary`2[System.Int32,System.Char]
```

>[!Info]
> The argument mustn't be a type that requires metadata annotations. Examples include the following types:
> - `dynamic`
> - `string?` (or any nullable reference type)


```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
