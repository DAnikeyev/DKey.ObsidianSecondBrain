---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [Collection Interface](Collection%20Interface.md)
___


## Properties

|   |   |
|---|---|
|[Current](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerator.current?view=net-9.0#system-collections-ienumerator-current)|Gets the element in the collection at the current position of the enumerator.|


## Methods

|                                                                                                                                                         |                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| [MoveNext()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerator.movenext?view=net-9.0#system-collections-ienumerator-movenext) | Advances the enumerator to the next element of the collection.                                    |
| [Reset()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerator.reset?view=net-9.0#system-collections-ienumerator-reset)          | Sets the enumerator to its initial position, which is before the first element in the collection. |

## Example

```cs
using System;
using System.Collections;

// Simple business object.
public class Person
{
    public Person(string fName, string lName)
    {
        this.firstName = fName;
        this.lastName = lName;
    }

    public string firstName;
    public string lastName;
}

// Collection of Person objects. This class
// implements IEnumerable so that it can be used
// with ForEach syntax.
public class People : IEnumerable
{
    private Person[] _people;
    public People(Person[] pArray)
    {
        _people = new Person[pArray.Length];

        for (int i = 0; i < pArray.Length; i++)
        {
            _people[i] = pArray[i];
        }
    }

// Implementation for the GetEnumerator method.
    IEnumerator IEnumerable.GetEnumerator()
    {
       return (IEnumerator) GetEnumerator();
    }

    public PeopleEnum GetEnumerator()
    {
        return new PeopleEnum(_people);
    }
}

// When you implement IEnumerable, you must also implement IEnumerator.
public class PeopleEnum : IEnumerator
{
    public Person[] _people;

    // Enumerators are positioned before the first element
    // until the first MoveNext() call.
    int position = -1;

    public PeopleEnum(Person[] list)
    {
        _people = list;
    }

    public bool MoveNext()
    {
        position++;
        return (position < _people.Length);
    }

    public void Reset()
    {
        position = -1;
    }

    object IEnumerator.Current
    {
        get
        {
            return Current;
        }
    }

    public Person Current
    {
        get
        {
            try
            {
                return _people[position];
            }
            catch (IndexOutOfRangeException)
            {
                throw new InvalidOperationException();
            }
        }
    }
}

class App
{
    static void Main()
    {
        Person[] peopleArray = new Person[3]
        {
            new Person("John", "Smith"),
            new Person("Jim", "Johnson"),
            new Person("Sue", "Rabon"),
        };

        People peopleList = new People(peopleArray);
        foreach (Person p in peopleList)
            Console.WriteLine(p.firstName + " " + p.lastName);
    }
}

/* This code produces output similar to the following:
 *
 * John Smith
 * Jim Johnson
 * Sue Rabon
 *
 */
```
## Applies to
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
