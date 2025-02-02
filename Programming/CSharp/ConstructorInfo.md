---
date_added: 2025-02-02
tags:
  - csharp
---
Up: [Reflection](Reflection.md)
___
Discovers the attributes of a class [[constructor]] and provides access to constructor metadata.
Use the [GetConstructors](https://learn.microsoft.com/en-us/dotnet/api/system.type.getconstructors) or [GetConstructor](https://learn.microsoft.com/en-us/dotnet/api/system.type.getconstructor) method of a [[Type]] to invoke a specific constructor.

```cs
using System;
using System.Reflection;
using System.Security;

public class MyClass3
{
    public MyClass3(int i) { }
    public static void Main()
    {
        try
        {
            Type myType = typeof(MyClass3);
            Type[] types = new Type[1];
            types[0] = typeof(int);
            // Get the public instance constructor that takes an integer parameter.
            ConstructorInfo constructorInfoObj = myType.GetConstructor(
                BindingFlags.Instance | BindingFlags.Public, null,
                CallingConventions.HasThis, types, null);
            if (constructorInfoObj != null)
            {
                Console.WriteLine("The constructor of MyClass3 that is a public " +
                    "instance method and takes an integer as a parameter is: ");
                Console.WriteLine(constructorInfoObj.ToString());
            }
            else
            {
                Console.WriteLine("The constructor of MyClass3 that is a public instance " +
                    "method and takes an integer as a parameter is not available.");
            }
        }
        catch (ArgumentNullException e)
        {
            Console.WriteLine("ArgumentNullException: " + e.Message);
        }
        catch (ArgumentException e)
        {
            Console.WriteLine("ArgumentException: " + e.Message);
        }
        catch (SecurityException e)
        {
            Console.WriteLine("SecurityException: " + e.Message);
        }
        catch (Exception e)
        {
            Console.WriteLine("Exception: " + e.Message);
        }
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
