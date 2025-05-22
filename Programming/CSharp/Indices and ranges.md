---
date_added: 2025-05-19
tags:
  - csharp
---
Up: [Collection](Collection.md)
___
## Indices
Indices let you refer to elements relative to the end of an array by using the ^
operator. ^1 refers to the last element, ^2 refers to the second-to-last element, and so
on:
## Ranges
Ranges let you “slice” an array by using the .. operator:

```cs
char[] firstTwo = vowels [..2]; // 'a', 'e'
char[] lastThree = vowels [2..]; // 'i', 'o', 'u'
char[] middleOne = vowels [2..3] // 'i'
char[] lastTwo = vowels [^2..]; // 'o', 'u'
```

Can be supported in your own classes via [CSharp Indexer](CSharp%20Indexer.md)
```cs
class Sentence
{
string[] words = "The quick brown fox".Split();
public string this [Index index] => words [index];
public string[] this [Range range] => words [range];
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
