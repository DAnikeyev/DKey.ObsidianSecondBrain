---
date_added: 2025-03-20
tags:
  - csharp
---
Up: [String](String.md)
___
 String interning is a memory optimization technique in .NET that ensures only one instance of each unique string value is stored in memory. The CLR (Common Language Runtime) maintains a special table called the "intern pool" or "string intern pool" that contains unique string references.

The purpose of interning is to optimize memory for repeated strings, but the runtime can't predict which dynamic strings will be repeated.
## Methods: 
 - String.Intern(string s) - checks if the string already exists in the pool:
	- If it exists, it returns a reference to the existing string
	- If it doesn't exist, it adds the string to the pool and returns a reference
- String.IsInterned
	- check if a string is already in the intern pool using
	- Returns the reference to the interned string if it exists in the pool, or null if it doesn't.
## Benefits of String Interning

1. **Memory Efficiency**: Only one instance of each unique string is stored in memory, which can save significant memory when your application uses many identical strings.
    
2. **Faster String Comparisons**: Comparing interned strings is very fast since the runtime can perform reference equality checks (`object.ReferenceEquals()` or the `\==` operator with cast to Object) instead of character-by-character comparisons.

```cs

string s1 = "MyTest";                                               
// Automatically interned

string s2 = new StringBuilder().Append("My").Append("Test").ToString(); 
// Not interned

string s3 = String.Intern(s2);                                      
// Manually interned

//**Compile-time constants** are also interned
const string Prefix = "Log_";
const string Suffix = "Entry";
const string FullName = Prefix + Suffix;
```

>[!Info]
> The string intern pool is shared across the entire application domain, so it needs to handle concurrent access properly.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
