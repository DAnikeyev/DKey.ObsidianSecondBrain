---
date_added: 2025-01-30
tags:
  - csharp
---
Up: [Other CSharp Features](Other%20CSharp%20Features.md)
___
 _Lazy initialization_ of an object means that its creation is deferred until it is first used.
## Basic Usage
 ```csharp
// Initialize by invoking a specific constructor on Order when Value
// property is accessed
Lazy<Orders> _orders = new Lazy<Orders>(() => new Orders(100));

// We need to create the array only if displayOrders is true
if (displayOrders == true)
{
    DisplayOrders(_orders.Value.OrderData);
}
else
{
    // Don't waste resources getting order data.
}
 ```

## Thread Safety
By deafault Lazy\<T> is thread safe. The Lazy<\T> class uses a [[lock]]
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
