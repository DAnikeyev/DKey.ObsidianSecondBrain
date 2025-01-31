---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [return](return.md) 
___
 By default, the `return` statement returns the value of an expression. You can return a reference to a variable. Reference return values (or ref returns) are values that a method returns by reference to the caller. That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object in the called method.
 ```cs
 int[] xs = new int [] {10, 20, 30, 40 };
ref int found = ref FindFirst(xs, s => s == 30);
found = 0;
Console.WriteLine(string.Join(" ", xs));  // output: 10 20 0 40

ref int FindFirst(int[] numbers, Func<int, bool> predicate)
{
    for (int i = 0; i < numbers.Length; i++)
    {
        if (predicate(numbers[i]))
        {
            return ref numbers[i];
        }
    }
    throw new InvalidOperationException("No element satisfies the given condition.");
}
```

## ref-safe context 
 - The return value must have a lifetime that extends beyond the execution of the method. In other words, it can't be a local variable in the method that returns it. It can be an instance or static field of a class
 - The return value can't be the literal `null`
 - The return value can't be a constant, an enumeration member, the by-value return value from a property, or a method of a `class` or `struct`.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
