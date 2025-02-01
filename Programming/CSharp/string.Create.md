---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [[string]]
___
 Is the way to create a string based on another string with limited extra memory allocation using [[Span T]]
  ```csharp  
    string s = "ABC";  
    //alphabet  
    var alp = string.Create(26, s, (span, value) =>  
    {  
        value.AsSpan().CopyTo(span);  
        for (int i = 3; i < span.Length; i++)  
        {            span[i] = (char)('A' + i);  
        }    
    });
    //alp is "A..Z"
 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
