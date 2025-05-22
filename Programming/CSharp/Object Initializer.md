---
date_added: 2025-05-22
tags:
  - csharp
---
Up: [Constructor](Constructor.md)
___
 Using object initializers, you can instantiate Bunny objects as follows:
```cs
// Note parameterless constructors can omit empty parentheses
Bunny b1 = new Bunny { Name="Bo", LikesCarrots=true, LikesHumans=false };
Bunny b2 = new Bunny ("Bo") { LikesCarrots=true, LikesHumans=false };
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
