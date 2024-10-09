---
date_added: 2024-10-09
tags:
  - design
---
Up: [SOLID principles](SOLID%20principles.md)
___
# Wrong Approach
```C#
public class Journal
{
	private readonly list<string> entries = new()
	public void AddEntry(string text)
	{
		entries.Add(text);
	}
	public void RemoveEntry(int index)
	{
		entries.RemoveAt(index)
	}
	public void Save(string filename, bool overwrite = false)
	{
		File.WriteAllText(filename, ToString());
	}
}
```
# Right approach
```C#
public class PersistenceManager 
{
	public void SaveToFile(Journal journal, string filename, bool overwrite = false) 
	{ 
		if (overwrite || !File.Exists(filename)) File.WriteAllText(filename, journal.ToString()); 
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
