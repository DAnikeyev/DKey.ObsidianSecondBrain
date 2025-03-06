---
date_added: 2025-03-06
tags:
  - csharp
---
Up: [[LINQ]]
___
 One of the most common uses of Expression Trees is in LINQ providers (like Entity Framework). When you write a LINQ query against a database the C# compiler converts this into an Expression Tree that the LINQ provider can analyze to generate the appropriate SQL query.
### 2. Dynamic Query Construction

Expression Trees allow building queries dynamically at runtime:

```cs
// Building a filter expression dynamically
ParameterExpression param = Expression.Parameter(typeof(Customer), "c");
Expression property = Expression.Property(param, "City");
Expression constant = Expression.Constant("London");
Expression condition = Expression.Equal(property, constant);
var lambda = Expression.Lambda<Func<Customer, bool>>(condition, param);

// Using the expression
var query = customers.Where(lambda.Compile());
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
