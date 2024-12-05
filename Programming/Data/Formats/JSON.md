---
date_added: 2024-11-14
tags:
  - data
  - format
---
Up: [Format](Format.md)
___
# Usage

Used for readable [[Serialization]] and [[Deserialization]] of data.
# Format

**JavaScript Object Notation** is a dictionary with possible types:
```JSON
{
	"string": "Hello",
	"number": 2,
	"boolean": true,
	"JSON object": 
	{
		"object key1": "world!",
		"object key2": false,
	},
	"null": null,
	"array": ["what", "is", "love"]
}
```

> [!info] Invalid types
>- a function
>- a date
>- _undefined_
# Extra
* Duplicates might be allowed, depending on the parser.
* Empty entries like "a":{} are allowed.
* Trailing commas are not allowed.
* Uses UTF-8 encoding.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
