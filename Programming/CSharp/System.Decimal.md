---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [Floating-point numeric type](Floating-point%20numeric%20type.md)
___
Decimal x = 10.123M;
28 digits precision, 16 bytes.

1. The decimal is stored in 128 bits split into four 32‑bit parts. Three of these (the low, middle, and high 32‑bit integers) together form a 96‑bit integer. This 96‑bit integer can be thought of as the "significand" that holds the digits of the number.
    
2. The remaining 32‑bit part is used as a flags word. In this flags word:
    
    - Bits 16–23 (8 bits) are used to store the scale factor, which specifies the number of digits to the right of the decimal point (from 0 to 28).
    - Bit 31 is used for the sign (0 for positive, 1 for negative).
    - The other bits in this word are reserved and not used.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
