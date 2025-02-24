---
date_added: 2025-02-21
tags:
  - csharp
---
Up: [SpecializedCollection](SpecializedCollection.md)
___
Creating case insensitive collections.

 ```cs
Hashtable population1 = CollectionsUtil.CreateCaseInsensitiveHashtable();
```

|                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [CreateCaseInsensitiveHashtable()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.collectionsutil.createcaseinsensitivehashtable?view=net-9.0#system-collections-specialized-collectionsutil-createcaseinsensitivehashtable)                                              | Creates a new case-insensitive instance of the [Hashtable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.hashtable?view=net-9.0) class with the default initial capacity.                                                                          |
| [CreateCaseInsensitiveHashtable(IDictionary)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.collectionsutil.createcaseinsensitivehashtable?view=net-9.0#system-collections-specialized-collectionsutil-createcaseinsensitivehashtable\(system-collections-idictionary\)) | Copies the entries from the specified dictionary to a new case-insensitive instance of the [Hashtable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.hashtable?view=net-9.0) class with the same initial capacity as the number of entries copied. |
| [CreateCaseInsensitiveHashtable(Int32)](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.collectionsutil.createcaseinsensitivehashtable?view=net-9.0#system-collections-specialized-collectionsutil-createcaseinsensitivehashtable\(system-int32\))                         | Creates a new case-insensitive instance of the [Hashtable](https://learn.microsoft.com/en-us/dotnet/api/system.collections.hashtable?view=net-9.0) class with the specified initial capacity.                                                                        |
| [CreateCaseInsensitiveSortedList()](https://learn.microsoft.com/en-us/dotnet/api/system.collections.specialized.collectionsutil.createcaseinsensitivesortedlist?view=net-9.0#system-collections-specialized-collectionsutil-createcaseinsensitivesortedlist)                                           | Creates a new instance of the [SortedList](https://learn.microsoft.com/en-us/dotnet/api/system.collections.sortedlist?view=net-9.0) class that ignores the case of strings.                                                                                          |

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
