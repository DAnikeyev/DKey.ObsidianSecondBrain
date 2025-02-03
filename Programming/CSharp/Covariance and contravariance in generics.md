---
date_added: 2025-01-27
tags:
  - csharp
---
Up: [Generic type parameters](Generic%20type%20parameters.md)
___
 When you're referring to a type system, covariance, contravariance, and invariance have the following definitions. The examples assume a base class named `Base` and a derived class named `Derived`.

- `Covariance`
    
    Enables you to use a more derived type than originally specified.
    
    You can assign an instance of `IEnumerable<Derived>` to a variable of type `IEnumerable<Base>` in .
    
- `Contravariance`
    
    Enables you to use a more generic (less derived) type than originally specified.
    
    You can assign an instance of `Action<Base>` to a variable of type `Action<Derived>`.
    
- `Invariance`
    
    Means that you can use only the type originally specified. An invariant generic type parameter is neither covariant nor contravariant.
    
    You cannot assign an instance of `List<Base>` to a variable of type `List<Derived>` or vice versa.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
