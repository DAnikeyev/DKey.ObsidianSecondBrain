---
date_added: 2025-01-24
tags:
  - csharp
---
Up: [Value Type](Value%20Type.md)
___
 Enumeration or `enum` type is a value type defined by a set of named constants of the underlying integral numeric type. 

```cs
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

by default assosiated constant has type int, but you can specify a different integral numeric type.

```cs
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

Methods are not allowed in `enum` type, but functionality can be added by using [[Extension method]].

## Flag enum

by using the `Flags` [[Attribute]], you can combine multiple values together.

```cs
[Flags]
public enum Days
{
    None      = 0b_0000_0000,  // 0
    Monday    = 0b_0000_0001,  // 1
    Tuesday   = 0b_0000_0010,  // 2
    Wednesday = 0b_0000_0100,  // 4
    Thursday  = 0b_0000_1000,  // 8
    Friday    = 0b_0001_0000,  // 16
    Saturday  = 0b_0010_0000,  // 32
    Sunday    = 0b_0100_0000,  // 64
    Weekend   = Saturday | Sunday
}

public class FlagsEnumExample
{
    public static void Main()
    {
        Days meetingDays = Days.Monday | Days.Wednesday | Days.Friday;
        Console.WriteLine(meetingDays);
        // Output:
        // Monday, Wednesday, Friday

        Days workingFromHomeDays = Days.Thursday | Days.Friday;
        Console.WriteLine($"Join a meeting by phone on {meetingDays & workingFromHomeDays}");
        // Output:
        // Join a meeting by phone on Friday

        bool isMeetingOnTuesday = (meetingDays & Days.Tuesday) == Days.Tuesday;
        Console.WriteLine($"Is there a meeting on Tuesday: {isMeetingOnTuesday}");
        // Output:
        // Is there a meeting on Tuesday: False

        var a = (Days)37;
        Console.WriteLine(a);
        // Output:
        // Monday, Wednesday, Saturday
    }
}
```

>[!Info]
> System.Enum is abstract base class that has functionality like `HasFlag`, `GetName`, `GetValues`, `Parse`, `ToObject`, `TryParse`.  System.Enum can be a constraint for generic type
> 
## Conversions

For any enumeration type, there exist explicit conversions between the enumeration type and its underlying integral type.
```cs
        var b = (Season)1;
        Console.WriteLine(b);  // output: Summer

        var c = (Season)4;
        Console.WriteLine(c);  // output: 4
```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
