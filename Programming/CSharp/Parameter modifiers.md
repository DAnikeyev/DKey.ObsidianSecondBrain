---
date_added: 2025-05-19
tags:
  - csharp
---
Up: [Parameters and arguments](Parameters%20and%20arguments.md)
___

|Parameter Modifier|Passed By|Variable Must Be Definitely Assigned|
|---|---|---|
|(None)|Value|Going In|
|ref|Reference|Going In|
|in|Reference (read-only)|Going In|
|out|Reference|Going Out|
### passing by reference

When you pass an argument by reference, you alias the storage location of an
existing variable rather than create a new storage location. In the following example,
the variables x and y represent the same instance:
```cs
class Test
{
	static int x;
	static void Main() { Foo (out x); }
	static void Foo (out int y)
	{
		Console.WriteLine (x); // x is 0
		y = 1; // Mutate y
		Console.WriteLine (x); // x is 1
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
