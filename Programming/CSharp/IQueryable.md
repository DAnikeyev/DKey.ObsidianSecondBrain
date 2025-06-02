---
date_added: 2025-02-24
tags:
  - csharp
---
Up: [Collection Interface](Collection%20Interface.md), [[LINQ]]
___
 `IQueryable<T>` is a generic interface that provides functionality to evaluate queries against a specific data source where the type of data is known. It inherits from [IEnumerable](IEnumerable.md) and `IQueryable`.

Local queries resolve to query operators in the Enumerable class (by default), which
in turn resolve to chains of decorator sequences. The delegates that they accept—
whether expressed in query syntax, fluent syntax, or traditional delegates—are fully
local to Intermediate Language (IL) code, just like any other C# method.

By contrast, interpreted queries are descriptive. They operate over sequences that
implement `IQueryable<T>`, and they resolve to the query operators in the Querya
ble class, which emit expression trees that are interpreted at runtime.

It’s also possible to generate an `IQueryable<T>` wrapper around an ordinary enumerable
collection by calling the AsQueryable method.

![](Pasted%20image%2020250602185658.png)

Queryable.Where accepts a predicate wrapped in an `Expression<TDelegate>`
type. This instructs the compiler to translate the supplied lambda expression—
in other words, n=>n.Name.Contains("a")—to an expression tree rather than a
compiled delegate. An expression tree is an object model based on the types in
System.Linq.Expressions that can be inspected at runtime (so that EF Core can
later translate it to an SQL statement).

>[!Info]
> Interpreted queries follow a deferred execution model—just like local queries.
## Properties

|   |   |
|---|---|
|[ElementType](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable.elementtype?view=net-9.0#system-linq-iqueryable-elementtype)|Gets the type of the element(s) that are returned when the expression tree associated with this instance of [IQueryable](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable?view=net-9.0) is executed.<br><br>(Inherited from [IQueryable](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable?view=net-9.0))|
|[Expression](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable.expression?view=net-9.0#system-linq-iqueryable-expression)|Gets the expression tree that is associated with the instance of [IQueryable](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable?view=net-9.0).<br><br>(Inherited from [IQueryable](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable?view=net-9.0))|
|[Provider](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable.provider?view=net-9.0#system-linq-iqueryable-provider)|Gets the query provider that is associated with this data source.<br><br>(Inherited from [IQueryable](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable?view=net-9.0))|

## Methods

|                                                                                                                                                                        |                                                                                                                                                                                           |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [GetEnumerator()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable.getenumerator?view=net-9.0#system-collections-ienumerable-getenumerator) | Returns an enumerator that iterates through a collection.<br><br>(Inherited from [IEnumerable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?view=net-9.0)) |

## Extension
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
