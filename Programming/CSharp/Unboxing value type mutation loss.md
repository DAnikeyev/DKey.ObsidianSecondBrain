---
date_added: 2025-03-10
tags:
  - csharp
---
Up: [Boxing and Unboxing](Boxing%20and%20Unboxing.md)
___
 ```cs
 internal struct Point
{
    private Int32 m_x, m_y;

    public Point(Int32 x, Int32 y)
    {
        m_x = x;
        m_y = y;
    }

    public void Change(Int32 x, Int32 y)
    {
        m_x = x;
        m_y = y;
    }

    public override String ToString()
    {
        return String.Format("({0}, {1})", m_x.ToString(), m_y.ToString());
    }
}

public sealed class Program
{
    public static void Main()
    {
        Point p = new Point(1, 1);
        Console.WriteLine(p);
        p.Change(2, 2);
        Console.WriteLine(p);

        Object o = p;
        Console.WriteLine(o);

        ((Point)o).Change(3, 3);
        Console.WriteLine(o);
    }
}
```

### Output
```cs
(1,1)
(2,2)
(2,2)
```

**`((Point)o).Change(3, 3);`**: This line attempts to change the boxed `Point`. However, because `o` is a boxed copy, this operation modifies a temporary copy of the `Point` and does not affect the original boxed object.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
