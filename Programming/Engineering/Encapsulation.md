---
date_added: 2025-01-11
tags:
  - design
---
Up: [Object-Oriented Programming](Object-Oriented%20Programming.md)
___
 Encapsulation is a concept that restricts direct access to some of an object's components. 
 
## **Why Do We Need It:**  
Encapsulation ensures that the internal representation of an object is hidden from the outside. It restricts direct access to some of an object's components, which helps in protecting the integrity of the data and prevents unintended interference.

## **How It's Used in Practice:**  
By using access modifiers (`private`, `public`, `protected`), developers can control how data within a class is accessed and modified. This leads to safer and more maintainable code by preventing external entities from putting objects into invalid states.


```C#
public class Person
{
    // Private field: cannot be accessed directly from outside the class
    private int age;

    // Public property with controlled access
    public int Age
    {
        get { return age; }
        set
        {
            if (value >= 0) // Validation logic
            {
                age = value;
            }
            else
            {
                throw new ArgumentException("Age cannot be negative.");
            }
        }
    }

    // Public method to display person's information
    public void DisplayInfo()
    {
        Console.WriteLine($"Age: {Age}");
    }
}

// Usage
Person person = new Person();
person.Age = 25;         // Valid assignment
person.DisplayInfo();   // Outputs: Age: 25
// person.Age = -5;      // Throws exception
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
