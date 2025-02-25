---
date_added: 2025-02-25
tags: []
---
Up: [Collection](Collection.md)
___
 Immutable collection that implements [ILookUp](ILookUp.md) and sequence of [IGrouping](IGrouping.md) 
 interfaces. and maps keys to collections of values.

```cs
System.Collections.Generic.IEnumerable
<System.Linq.IGrouping<TKey,TElement>>
```
### Example

```cs
        // Sample list of products
        List<Product> products = new List<Product>
        {
            new Product { Category = "Electronics", Name = "Laptop" },
            new Product { Category = "Electronics", Name = "Smartphone" },
            new Product { Category = "Clothing", Name = "T-Shirt" },
            new Product { Category = "Clothing", Name = "Jeans" }
        };

        // Create the lookup using the Category as the key
        ILookup<string, Product> lookup = products.ToLookup(product => product.Category);

        // Iterate over each group in the lookup
        foreach (var group in lookup)
        {
            Console.WriteLine($"Category: {group.Key}");
            foreach (var product in group)
            {
                Console.WriteLine($"  - {product.Name}");
            }
        }
```

## When to Use Lookup

- **Grouping Data:** When you need to group elements based on a key and later retrieve all elements for a specific group.
- **Read-Only Grouping:** When you want a snapshot of grouped data that will not be modified.
- **Simplification:** Instead of manually grouping data with a dictionary, a lookup provides a clean, concise way to perform grouping operations.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
