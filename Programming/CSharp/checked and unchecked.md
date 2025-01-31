---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [CSharp Statement](CSharp%20Statement.md)
___
 The `checked` and `unchecked` statements specify the overflow-checking context for integral-type arithmetic operations and conversions. by-default behavior is `unchecked`. When an `unchecked` statement is used, the overflow is not checked, and the result is truncated by discarding high-order bits. 
## Usage

You can use the `checked` modifier only when you overload any of the following operators:

- Unary `++`, `--`, and `-` operators
- Binary `*`, `/`, `+`, and `-` operators
- Explicit [Custom Conversion Operators](Custom%20Conversion%20Operators.md) 
 
  ```csharp
 uint a = uint.MaxValue;

unchecked
{
    Console.WriteLine(a + 3);  // output: 2
}

try
{
    checked
    {
        Console.WriteLine(a + 3);
    }
}
catch (OverflowException e)
{
    Console.WriteLine(e.Message);  // output: Arithmetic operation resulted in an overflow.
}
 ```

## User-defined checked operators.

```cs
public record struct Point(int X, int Y)
{
    public static Point operator checked +(Point left, Point right)
    {
        checked
        {
            return new Point(left.X + right.X, left.Y + right.Y);
        }
    }
    
    public static Point operator +(Point left, Point right)
    {
        return new Point(left.X + right.X, left.Y + right.Y);
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
