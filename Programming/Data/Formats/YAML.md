---
date_added: 2024-11-14
tags:
  - Data
---
Up: [Format](Format.md)
___
# Usage
Used for readable [[Serialization]] and [[Deserialization]] of data. Yaml Ain't Markup Language.
# Syntax 
Consist mostly of key value pairs. Space indentation is used instead of brackets. 
```yaml
#Comment
key1: value
"key2 with list": 
  - value1
  - value2
"key2 with object": 
  key: value
  key: http://www.wikipedia.org
---# three dashes denotes a document boundary
"key3 with string": 'value''s apostrophe'
{InlineObject: value1, SameAs2Lines: value2}
...# optional three dots denotes the end of a document
```
* quotes are optional for strings.
* lists are denoted by `-`
* objects are denoted by indentation.
* space after colon is mandatory so links doesn't have to be put in quotes.
* comments are denoted by `#`
* single quoted string doesn't allow escape characters except double single quote  ''.
* double quoted string allows escape characters.
* tabs are not allowed.
* | preserves new lines, while > folds them.
* you can use more than 1 space for indentation after ":" .

```YAML
data: |
   There once was a tall man from Ealing
   Who got on a bus to Darjeeling
       It said on the door
       "Please don't sit on the floor"
   So he carefully sat on the ceiling
data: >
   Wrapped text
   will be folded
   into a single
   paragraph

   Blank lines denote
   paragraph breaks
```
# Anchors
```yaml
--- # Sequencer protocols for Laser eye surgery
- step:  &id001                  # defines anchor label &id001
    instrument:      Lasik 2000
    pulseEnergy:     5.4
    pulseDuration:   12
    repetition:      1000
    spotSize:        1mm

- step: &id002
    instrument:      Lasik 2000
    pulseEnergy:     5.0
    pulseDuration:   10
    repetition:      500
    spotSize:        2mm
- Instrument1: *id001   # refers to the first step (with anchor &id001)
- Instrument2: *id002   # refers to the second step
```


# Data Types
* string
* number
* boolean
* object
* null
* list
```Yaml
---
a: 123                     # an integer
b: "123"                   # a string, disambiguated by quotes
c: 123.0                   # a float
d: !!float 123             # also a float via explicit data type prefixed by (!!)
e: !!str 123               # a string, disambiguated by explicit type
f: !!str Yes               # a string via explicit type
g: Yes                     # a Boolean True (yaml1.1), string "Yes" (yaml1.2)
h: Yes we have No bananas  # a string, "Yes" and "No" disambiguated by context.
```
# Extra
* Yaml has flaws like significant whitespaces and ambiguity. [StrictYaml](https://github.com/crdoconnor/strictyaml) is one of the alternatives. Not as good as JSON for data exchange, but better for configuration files.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
