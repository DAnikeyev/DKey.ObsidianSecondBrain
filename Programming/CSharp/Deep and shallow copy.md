---
date_added: 2025-02-19
tags:
  - csharp
---
Up: [Object](Object.md)
___
MemberwiseClone creates a Shallow copy of object. So references are copied as is, without creating a new object. That can lead to a problem when changing copied character changes original. To prevent this a Deep copy mechanism must be used, where all reference values are copied manually:

 ```csharp
 
using System;

public class IdInfo
{
    public int IdNumber;

    public IdInfo(int IdNumber)
    {
        this.IdNumber = IdNumber;
    }
}

public class Person
{
    public int Age;
    public string Name;
    public IdInfo IdInfo;

    public Person ShallowCopy()
    {
        return (Person)MemberwiseClone();
    }

    public Person DeepCopy()
    {
        Person other = (Person)MemberwiseClone();
        other.IdInfo = new IdInfo(IdInfo.IdNumber);
        return other;
    }
}
```

To copyDeep automatically you can use different approaches:
 - Reflection
 - Serialization
 - Library like AutoMapper or DeepCloner

Example:

 ```csharp
using System;
using System.Reflection;

public static class ObjectExtensions
{
    public static T DeepCopy<T>(this T original)
    {
        if (original == null)
        {
            return default;
        }

        // Create a new instance of the object
        T copy = (T)Activator.CreateInstance(original.GetType());

        // Get all public fields of the object
        FieldInfo[] fields = original.GetType().GetFields(BindingFlags.Public | BindingFlags.Instance);

        foreach (FieldInfo field in fields)
        {
            object originalValue = field.GetValue(original);

            // If the field is a value type or string, assign directly
            if (field.FieldType.IsValueType || field.FieldType == typeof(string))
            {
                field.SetValue(copy, originalValue);
            }
            else
            {
                // For reference types, recursively call DeepCopy
                object copiedValue = originalValue.DeepCopy();
                field.SetValue(copy, copiedValue);
            }
        }

        return copy;
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
