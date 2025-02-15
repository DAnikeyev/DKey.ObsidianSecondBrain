---
date_added: 2025-02-15
tags:
  - csharp
---
Up: [NUnit](NUnit.md)
___
`Assert` is a class that provides a set of static methods used to verify conditions in unit tests.

## Examples:
```cs
Assert.AreEqual(5, 2 + 3); // Checks if 2 + 3 equals 5
Assert.AreNotEqual(4, 2 + 3); // Checks if 2 + 3 is not 4
Assert.IsTrue(2 + 2 == 4); // Checks if condition is true
Assert.IsFalse(2 + 2 == 5); // Checks if condition is false
Assert.IsNull(null); // Checks if object is null
Assert.IsNotNull(new object()); // Checks if object is not null
Assert.IsInstanceOf(typeof(string), "Hello"); // Checks if object is of type string
Assert.Throws<DivideByZeroException>(() => { int x = 0; int y = 1 / x; }); // Verifies exception thrown
Assert.DoesNotThrow(() => { int x = 1; int y = 2; int z = y / x; }); // Verifies no exception thrown
Assert.Contains(10, new[] { 5, 10, 15 }); // Checks if collection contains a specific value

Assert.That(2 + 2, Is.EqualTo(4)); // Uses the constraint model to check equality
Assert.That("Hello World", Does.StartWith("Hello")); // Checks if string starts with a specific substring
Assert.That("Hello World", Does.Contain("World")); // Checks if string contains a specific substring 
Assert.That(new[] { 1, 2, 3 }, Is.All.GreaterThan(0)); // Checks if all elements in the collection are greater than 0 
Assert.That(() => { throw new InvalidOperationException(); }, Throws.TypeOf<InvalidOperationException>()); // Verifies specific exception type is thrown
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
