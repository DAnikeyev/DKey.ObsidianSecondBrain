---
date_added: 2024-10-31
tags:
  - data
  - format
---
Up: [Format](Format.md)
___
  ```
  # Header
  ## Header 2
  ### Header 3
  #### Header 4
  ##### Header 5
  ###### Header 6

  Alternatively,
  
  Alt Header1
  ======
  
  Alt Header2
  ------
  ```
# Header
  
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6
  
Alt Header1
======
  
Alt Header2
------

```
Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks_ and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~
```

Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~

```
1. First ordered list item
2. Another item
⋅⋅* Unordered sub-list. 
1. Actual numbers don't matter, just that it's a number
⋅⋅1. Ordered sub-list
4. And another item.

⋅⋅⋅You can have properly indented paragraphs within list items. Notice the blank line above, and the leading spaces (at least one, but we'll use three here to also align the raw Markdown).

⋅⋅⋅To have a line break without a paragraph, you will need to use two trailing spaces.⋅⋅
⋅⋅⋅Note that this line is separate, but within the same paragraph.⋅⋅
⋅⋅⋅(This is contrary to the typical GFM line break behaviour, where trailing spaces are not required.)

* Unordered list can use asterisks
- Or minuses
+ Or pluses
```


1. First ordered list item
   * Shift click + * for unordered sub-list
2. Another item
3. Actual numbers don't matter, just that it's a number
   1. Ordered sub-list
   2. Ordered sub-list
      + pluses or minuses
        - behave the same way

# Links

There are two ways to create links.

```
[Link Text](URL)
[Link Text](URL "Title")
[[ObsidianLink|link]]

[I'm a reference-style link][Arbitrary case-insensitive reference text]

[I'm a relative reference to a repository file](../blob/master/LICENSE)

[You can use numbers for reference-style link definitions][1]

Or leave it empty and use the [link text itself].

URLs and URLs in angle brackets will automatically get turned into links. 
http://www.example.com or <http://www.example.com> and sometimes 
example.com (but not on Github, for example).

Some text to show that the reference links can follow later.

[arbitrary case-insensitive reference text]: https://www.mozilla.org
[1]: http://slashdot.org
[link text itself]: http://www.reddit.com
```

[Link Text](Format.md)
[Link Text](Format.md "Title")
[[Obsidian Link|link]]

[I'm a reference-style link][Arbitrary case-insensitive reference text]

[I'm a relative reference to a repository file](Learning.md)

[You can use numbers for reference-style link definitions][1]

Or leave it empty and use the [link text itself].

URLs and URLs in angle brackets will automatically get turned into links. 
http://www.example.com or <http://www.example.com> and sometimes 
example.com (but not on Github, for example).

Some text to show that the reference links can follow later.

[arbitrary case-insensitive reference text]: https://www.mozilla.org
[1]: http://slashdot.org
[link text itself]: http://www.reddit.com

```
Here's our logo (hover to see the title text):

Inline-style: 
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

Reference-style: 
![alt text][logo]

[logo]: https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 2"
```

Here's our logo (hover to see the title text):

Inline-style: 
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

Reference style doesn't work in obsidian

# Code
````
```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```
 
```python
s = "Python syntax highlighting"
print s
```
 
```
No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
```
````

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```
 
```python
s = "Python syntax highlighting"
print s
```

```csharp
using (var s = "C# syntax highlighting")
{
    Console.WriteLine(s);
}
```
```
No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
```
# Math
using [Latex](Latex.md)
```
	$$ \frac {Latex}{format} $$
	$\text{Also inline} \sum_{Latex}^{Format}$
```
	$$ \frac {Latex}{format} $$$\text{Also inline} \underline{\sum_{i = Latex}^{Format} x_i^2= -1}_{\text{some nonsence}} => \pi \in \mathbb{R}$
# Tables
```
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
```


| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
# BlockQuotes

```
> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote.
```


> [!info] this line is optional
> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote.

# HTML
you can use [[HTML]] 
```
<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>
```

<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>
# Separators

Three or more...

---

Hyphens

***

Asterisks

___

Underscores
### Callout types
1. `>[!note]` - General notes.
2. `>[!info]` - Information.
3. `>[!tip]` - Tips or helpful hints.
4. `>[!success]` - Success messages.
5. `>[!question]` - Questions or prompts for further thought.
6. `>[!warning]` - Warnings about potential issues.
7. `>[!failure]` - Failure or error messages.
8. `>[!danger]` - Dangerous or critical warnings.
9. `>[!bug]` - Bug reports or issues.
10. `>[!example]` - Examples or illustrations.
11. `>[!quote]` - Quotes or citations.
12. `>[!abstract]` - Abstracts or summaries.
13. `>[!summary]` - Summaries or conclusions.
14. `>[!tldr]` - "Too long; didn't read" summaries.
15. `>[!important]` - Important information.
16. `>[!caution]` - Cautionary notes.
>[!note] - General notes.

>[!info] - Information.

>[!tip] - Tips or helpful hints.

>[!success] - Success messages.

>[!question] - Questions or prompts for further thought.

>[!warning] - Warnings about potential issues.

>[!failure] - Failure or error messages.

>[!danger] - Dangerous or critical warnings.

>[!bug] - Bug reports or issues.

>[!example] - Examples or illustrations.

>[!quote] - Quotes or citations.

>[!abstract] - Abstracts or summaries.

>[!summary] - Summaries or conclusions.

>[!tldr] - "Too long; didn't read" summaries.

>[!important] - Important information.

>[!caution] - Cautionary notes.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
# Reference
https://github.com/adam-p/markdown-here/wiki/markdown-cheatsheet