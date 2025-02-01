---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [Memory buffers](Memory%20buffers.md)
___
 SearchValues is particularly useful when:

- Performing character validation
- Parsing [String](String.md) efficiently
- Implementing custom string processing
- Need high-performance pattern matching
- Working with spans of data

The main advantages of SearchValues are:

- Efficient pattern matching
- No allocations during searches
- Works well with Span and ReadOnlySpan
- Can be reused across multiple operations
- Optimized for performance
## Examples
```cs
using System.Buffers;

public class BasicSearchValuesExample
{
    public void BasicUsage()
    {
        // Create SearchValues for characters
        SearchValues<char> vowels = SearchValues.Create("aeiou");
        
        string text = "Hello World";
        // Check if contains any vowels
        bool hasVowels = text.AsSpan().ContainsAny(vowels);
        
        // Check if contains only vowels
        bool onlyVowels = !text.AsSpan().ContainsAnyExcept(vowels);
    }
}
```

```cs
public class StringProcessor
{
    private readonly SearchValues<char> _separators;
    private readonly SearchValues<char> _whitespace;

    public StringProcessor()
    {
        _separators = SearchValues.Create(",.;:!?");
        _whitespace = SearchValues.Create(" \t\n\r");
    }

    public bool IsValidSentence(ReadOnlySpan<char> text)
    {
        // Check if starts with capital letter
        if (text.IsEmpty || !char.IsUpper(text[0]))
            return false;

        // Check if ends with valid separator
        if (!text.EndsWith(".") && !text.EndsWith("!") && !text.EndsWith("?"))
            return false;

        // Check if contains only valid characters
        return !text.ContainsAnyExcept(
            SearchValues.Create("ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz .,!?"));
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
