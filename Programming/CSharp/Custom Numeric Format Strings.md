---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [String Formating](String%20Formating.md)
___

|Format specifier|Name|Description|Examples|
|---|---|---|---|
|"0"|Zero placeholder|Replaces the zero with the corresponding digit if one is present; otherwise, zero appears in the result string.  <br>  <br>More information: [The "0" Custom Specifier](https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings#Specifier0).|1234.5678 ("00000") -> 01235  <br>  <br>0.45678 ("0.00", en-US) -> 0.46  <br>  <br>0.45678 ("0.00", fr-FR) -> 0,46|
|"#"|Digit placeholder|Replaces the "#" symbol with the corresponding digit if one is present; otherwise, no digit appears in the result string.  <br>  <br>Note that no digit appears in the result string if the corresponding digit in the input string is a non-significant 0. For example, 0003 ("####") -> 3.  <br>  <br>More information: [The "#" Custom Specifier](https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings#SpecifierD).|1234.5678 ("#####") -> 1235  <br>  <br>0.45678 ("#.##", en-US) -> .46  <br>  <br>0.45678 ("#.##", fr-FR) -> ,46|
|"."|Decimal point|Determines the location of the decimal separator in the result string.  <br>  <br>More information: [The "." Custom Specifier](https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings#SpecifierPt).|0.45678 ("0.00", en-US) -> 0.46  <br>  <br>0.45678 ("0.00", fr-FR) -> 0,46|
|","|Group separator and number scaling|Serves as both a group separator and a number scaling specifier. As a group separator, it inserts a localized group separator character between each group. As a number scaling specifier, it divides a number by 1000 for each comma specified.  <br>  <br>More information: [The "," Custom Specifier](https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings#SpecifierTh).|Group separator specifier:  <br>  <br>2147483647 ("##,#", en-US) -> 2,147,483,647  <br>  <br>2147483647 ("##,#", es-ES) -> 2.147.483.647  <br>  <br>Scaling specifier:  <br>  <br>2147483647 ("#,#,,", en-US) -> 2,147  <br>  <br>2147483647 ("#,#,,", es-ES) -> 2.147|
|"%"|Percentage placeholder|Multiplies a number by 100 and inserts a localized percentage symbol in the result string.  <br>  <br>More information: [The "%" Custom Specifier](https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings#SpecifierPct).|0.3697 ("%#0.00", en-US) -> %36.97  <br>  <br>0.3697 ("%#0.00", el-GR) -> %36,97  <br>  <br>0.3697 ("##.0 %", en-US) -> 37.0 %  <br>  <br>0.3697 ("##.0 %", el-GR) -> 37,0 %|
|"‰"|Per mille placeholder|Multiplies a number by 1000 and inserts a localized per mille symbol in the result string.  <br>  <br>More information: [The "‰" Custom Specifier](https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings#SpecifierPerMille).|0.03697 ("#0.00‰", en-US) -> 36.97‰  <br>  <br>0.03697 ("#0.00‰", ru-RU) -> 36,97‰|
|"E0"  <br>  <br>"E+0"  <br>  <br>"E-0"  <br>  <br>"e0"  <br>  <br>"e+0"  <br>  <br>"e-0"|Exponential notation|If followed by at least one 0 (zero), formats the result using exponential notation. The case of "E" or "e" indicates the case of the exponent symbol in the result string. The number of zeros following the "E" or "e" character determines the minimum number of digits in the exponent. A plus sign (+) indicates that a sign character always precedes the exponent. A minus sign (-) indicates that a sign character precedes only negative exponents.  <br>  <br>More information: [The "E" and "e" Custom Specifiers](https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings#SpecifierExponent).|987654 ("#0.0e0") -> 98.8e4  <br>  <br>1503.92311 ("0.0##e+00") -> 1.504e+03  <br>  <br>1.8901385E-16 ("0.0e+00") -> 1.9e-16|
|"\"|Escape character|Causes the next character to be interpreted as a literal rather than as a custom format specifier.  <br>  <br>More information: [The "\" Escape Character](https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings#SpecifierEscape).|987654 ("\###00\#") -> #987654#|
|'_string_'  <br>  <br>"_string_"|Literal string delimiter|Indicates that the enclosed characters should be copied to the result string unchanged.  <br>  <br>More information: [Character literals](https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings#character-literals).|68 ("# 'degrees'") -> 68 degrees  <br>  <br>68 ("#' degrees'") -> 68 degrees|
|;|Section separator|Defines sections with separate format strings for positive, negative, and zero numbers.  <br>  <br>More information: [The ";" Section Separator](https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings#SectionSeparator).|12.345 ("#0.0#;(#0.0#);-\0-") -> 12.35  <br>  <br>0 ("#0.0#;(#0.0#);-\0-") -> -0-  <br>  <br>-12.345 ("#0.0#;(#0.0#);-\0-") -> (12.35)  <br>  <br>12.345 ("#0.0#;(#0.0#)") -> 12.35  <br>  <br>0 ("#0.0#;(#0.0#)") -> 0.0  <br>  <br>-12.345 ("#0.0#;(#0.0#)") -> (12.35)|
|Other|All other characters|The character is copied to the result string unchanged.  <br>  <br>More information: [Character literals](https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-numeric-format-strings#character-literals).|68 ("# °") -> 68 °|

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
