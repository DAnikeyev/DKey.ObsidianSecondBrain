---
date_added: 2025-03-20
tags:
  - csharp
---
Up: [High-Performance strategies](High-Performance%20strategies.md)
___
### Static cache

If you need to calculate a value only once and then reuse it, you can use a static cache. This is useful when the calculation is expensive and the result is immutable.
```cs
var allCampaignStatuses = 
   ((CampaignActivityStatus[])Enum.GetValues(typeof(CampaignActivityStatus)))
   .ToList();
```

## [[IMemoryCache]]
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
