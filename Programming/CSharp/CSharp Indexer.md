---
date_added: 2025-01-21
tags:
  - csharp
---
Up: [[Class]]
___
using method like T this[int i] you can index a class or struct like an array or another [[Collection]]. 

```cs
namespace Indexers;

public class SampleCollection<T>
{
   // Declare an array to store the data elements.
   private T[] arr = new T[100];

   // Define the indexer to allow client code to use [] notation.
   public T this[int i]
   {
      get => arr[i];
      set => arr[i] = value;
   }
}
```

Can also be declared as property: 
```cs
namespace Indexers;

public class ReadOnlySampleCollection<T>(params IEnumerable<T> items)
{
   // Declare an array to store the data elements.
   private T[] arr = [.. items];

   public T this[int i] => arr[i];

}
```
## Comparison with [Property](Property.md)

| Property                                                                                                                                                                                  | Indexer                                                                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Allows methods to be called as if they were public data members.                                                                                                                          | Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.                                                                                     |
| Accessed through a simple name.                                                                                                                                                           | Accessed through an index.                                                                                                                                                                              |
| Can be a static or an instance member.                                                                                                                                                    | Must be an instance member.                                                                                                                                                                             |
| A [get](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/get) accessor of a property has no parameters.                                                        | A `get` accessor of an indexer has the same formal parameter list as the indexer.                                                                                                                       |
| A [set](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/set) accessor of a property contains the implicit `value` parameter.                                  | A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/value) parameter. |
| Supports shortened syntax with [Automatically implemented properties](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties). | Supports expression bodied members for get only indexers.                                                                                                                                               |
## Restrictions

>[!Info]
> The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself


>[!Info]
> Can be used in interfaces witout access modifiers and body



## Use case
If API models a collection of items, you can use an indexer to access items by index. 

Can also be used as a dictionary:
```cs
namespace Indexers;
public class ArgsProcessor
{
    private readonly ArgsActions _actions;

    public ArgsProcessor(ArgsActions actions)
    {
        _actions = actions;
    }

    public void Process(string[] args)
    {
        foreach (var arg in args)
        {
            _actions[arg]?.Invoke();
        }
    }

}
public class ArgsActions
{
    readonly private Dictionary<string, Action> _argsActions = new();

    public Action this[string s]
    {
        get
        {
            Action? action;
            Action defaultAction = () => { };
            return _argsActions.TryGetValue(s, out action) ? action : defaultAction;
        }
    }

    public void SetOption(string s, Action a)
    {
        _argsActions[s] = a;
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
