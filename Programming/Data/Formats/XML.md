---
date_added: 2025-01-10
tags:
  - data
---
Up: [Format](Format.md)
___
Extensible Markup Language (XML) is a markup language that defines a set of rules for encoding documents in a format that is both ==human-readable and machine-readable==. Creates a tree-like structure of elements and attributes.


# Terminology

- Character: An XML document is a string of characters. Every legal Unicode character (except Null) may appear in an (1.1) XML document
- **Element**: A building block of XML. It starts with a start tag and ends with an end tag or is empty. It can contain other elements (Aka Child elements), text, or attributes.
- Markup: The characters making up an XML document are divided into markup and content, which may be distinguished by the application of simple syntactic rules. Generally, strings that constitute markup either begin with the character < and end with a >, or they begin with the character & and end with a ;. Strings of characters that are not markup are content. However, in a CDATA section, the delimiters ==<![CDATA[ and ]]>== are classified as markup, while the text between them is classified as content. In addition, whitespace before and after the outermost element is classified as markup.
- Tag
	- _start-tag_, such as `<section>`;
	- _end-tag_, such as `</section>`;
	- _empty-element tag_, such as `<line-break />`.
- XML Declaration: Meta Information`<?xml version="1.0" encoding="UTF-8"?>`
- XML Processor: Parser that reads XML and transforms it to the data structure desirable for the application.
- Attribute: A name-value pair that exists within a start-tag or empty-element tag. The values are quoted. `<img src="madonna.jpg" alt="Madonna" />`
>[!Info]
>An XML attribute can only have a single value and each attribute can appear at most once on each element. In the common situation where a list of multiple values is desired, this must be done by encoding the list into a well-formed XML attribute

# Escaping
- `&lt;` for `<`
- `&gt;` for `>`
- `&amp;` for `&`
- `&apos;` for `'`
- `&quot;` for `"`
# Validating 
While expecting a certain structure, XML can be validated against a schema. 
- DTD: Document Type Definition
- XSD: XML Schema Definition
# Example

```XML
<friendList>
  <friend>
    <name>John</name>
    <age>25</age>
  </friend>
  <friend>
    <name>Jane</name>
    <age>22</age>
  </friend>
  <bestFriend>
    <name>Jack</name>
    <age>30</age>
  </bestFriend>
</friendList>
```

### Comments
```XML
	<!-- This is a comment -->
```

### CDATA

**CDATA sections** may occur anywhere character data may occur; they are used to escape blocks of text containing characters which would otherwise be recognized as markup. CDATA sections begin with the string " `<![CDATA[` " and end with the string " `]]>` "
```XML
  <![CDATA[This is a CDATA section]]>
```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
