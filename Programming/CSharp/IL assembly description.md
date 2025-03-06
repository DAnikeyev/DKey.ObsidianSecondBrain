---
date_added: 2025-03-06
tags:
  - csharp
---
Up: [Intermediate Language](Intermediate%20Language.md)
___
 ```cs
 .assembly extern System.Console
{
  .publickeytoken = ( B0 3F 5F 7F 11 D5 0A 3A ) // .._.....
  .ver 8:0:0:0
}
```

## Strong name

is a unique identifier of assembly.
Here are the main components:  
 - Assembly Name: The name of the assembly.
 - Version Number: The version of the assembly.
 - Culture Information: Optional information about the culture or language the assembly supports.
 - Public Key: A unique key that identifies the publisher of the assembly.
 - Digital Signature: A cryptographic signature that ensures the assembly has not been tampered with.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
