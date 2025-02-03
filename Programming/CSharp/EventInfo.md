---
date_added: 2025-02-03
tags:
  - csharp
---
Up: [Reflection](Reflection.md)
___
is used to to discover information such as the name, event-handler data type, custom attributes, declaring type, and reflected type of an event, and to add or remove event handlers
```cs
using System;
using System.Reflection;
using System.Security;

class MyEventExample
{
    public static void Main()
    {
        try
        {

            // Creates a bitmask based on BindingFlags.
            BindingFlags myBindingFlags = BindingFlags.Instance | BindingFlags.Public | BindingFlags.NonPublic;
            Type myTypeBindingFlags = typeof(System.Windows.Forms.Button);
            EventInfo myEventBindingFlags = myTypeBindingFlags.GetEvent("Click", myBindingFlags);
            if(myEventBindingFlags != null)
            {
                Console.WriteLine("Looking for the Click event in the Button class with the specified BindingFlags.");
                Console.WriteLine(myEventBindingFlags.ToString());
            }
            else
            {
                Console.WriteLine("The Click event is not available with the Button class.");
            }
        }
        catch(SecurityException e)
        {
            Console.WriteLine("An exception occurred.");
            Console.WriteLine("Message :"+e.Message);
        }
        catch(ArgumentNullException e)
        {
            Console.WriteLine("An exception occurred.");
            Console.WriteLine("Message :"+e.Message);
        }
        catch(Exception e)
        {
            Console.WriteLine("The following exception was raised : {0}",e.Message);
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
