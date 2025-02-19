---
date_added: 2025-02-19
tags:
  - csharp
---
Up: [Fundamental Interfaces](Fundamental%20Interfaces.md)
___

>[!Info]
> 
If you implement the [IConvertible](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible?view=net-9.0) interface, your implementation will be called automatically by the [ChangeType(Object, Type)](https://learn.microsoft.com/en-us/dotnet/api/system.convert.changetype?view=net-9.0#system-convert-changetype\(system-object-system-type\)) method if the [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0) parameter is an instance of your implementing type and the [Type](https://learn.microsoft.com/en-us/dotnet/api/system.type?view=net-9.0) parameter is a common language runtime type.

## Methods

|   |   |
|---|---|
|[GetTypeCode()](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.gettypecode?view=net-9.0#system-iconvertible-gettypecode)|Returns the [TypeCode](https://learn.microsoft.com/en-us/dotnet/api/system.typecode?view=net-9.0) for this instance.|
|[ToBoolean(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.toboolean?view=net-9.0#system-iconvertible-toboolean\(system-iformatprovider\))|Converts the value of this instance to an equivalent Boolean value using the specified culture-specific formatting information.|
|[ToByte(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.tobyte?view=net-9.0#system-iconvertible-tobyte\(system-iformatprovider\))|Converts the value of this instance to an equivalent 8-bit unsigned integer using the specified culture-specific formatting information.|
|[ToChar(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.tochar?view=net-9.0#system-iconvertible-tochar\(system-iformatprovider\))|Converts the value of this instance to an equivalent Unicode character using the specified culture-specific formatting information.|
|[ToDateTime(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.todatetime?view=net-9.0#system-iconvertible-todatetime\(system-iformatprovider\))|Converts the value of this instance to an equivalent [DateTime](https://learn.microsoft.com/en-us/dotnet/api/system.datetime?view=net-9.0) using the specified culture-specific formatting information.|
|[ToDecimal(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.todecimal?view=net-9.0#system-iconvertible-todecimal\(system-iformatprovider\))|Converts the value of this instance to an equivalent [Decimal](https://learn.microsoft.com/en-us/dotnet/api/system.decimal?view=net-9.0) number using the specified culture-specific formatting information.|
|[ToDouble(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.todouble?view=net-9.0#system-iconvertible-todouble\(system-iformatprovider\))|Converts the value of this instance to an equivalent double-precision floating-point number using the specified culture-specific formatting information.|
|[ToInt16(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.toint16?view=net-9.0#system-iconvertible-toint16\(system-iformatprovider\))|Converts the value of this instance to an equivalent 16-bit signed integer using the specified culture-specific formatting information.|
|[ToInt32(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.toint32?view=net-9.0#system-iconvertible-toint32\(system-iformatprovider\))|Converts the value of this instance to an equivalent 32-bit signed integer using the specified culture-specific formatting information.|
|[ToInt64(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.toint64?view=net-9.0#system-iconvertible-toint64\(system-iformatprovider\))|Converts the value of this instance to an equivalent 64-bit signed integer using the specified culture-specific formatting information.|
|[ToSByte(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.tosbyte?view=net-9.0#system-iconvertible-tosbyte\(system-iformatprovider\))|Converts the value of this instance to an equivalent 8-bit signed integer using the specified culture-specific formatting information.|
|[ToSingle(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.tosingle?view=net-9.0#system-iconvertible-tosingle\(system-iformatprovider\))|Converts the value of this instance to an equivalent single-precision floating-point number using the specified culture-specific formatting information.|
|[ToString(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.tostring?view=net-9.0#system-iconvertible-tostring\(system-iformatprovider\))|Converts the value of this instance to an equivalent [String](https://learn.microsoft.com/en-us/dotnet/api/system.string?view=net-9.0) using the specified culture-specific formatting information.|
|[ToType(Type, IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.totype?view=net-9.0#system-iconvertible-totype\(system-type-system-iformatprovider\))|Converts the value of this instance to an [Object](https://learn.microsoft.com/en-us/dotnet/api/system.object?view=net-9.0) of the specified [Type](https://learn.microsoft.com/en-us/dotnet/api/system.type?view=net-9.0) that has an equivalent value, using the specified culture-specific formatting information.|
|[ToUInt16(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.touint16?view=net-9.0#system-iconvertible-touint16\(system-iformatprovider\))|Converts the value of this instance to an equivalent 16-bit unsigned integer using the specified culture-specific formatting information.|
|[ToUInt32(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.touint32?view=net-9.0#system-iconvertible-touint32\(system-iformatprovider\))|Converts the value of this instance to an equivalent 32-bit unsigned integer using the specified culture-specific formatting information.|
|[ToUInt64(IFormatProvider)](https://learn.microsoft.com/en-us/dotnet/api/system.iconvertible.touint64?view=net-9.0#system-iconvertible-touint64\(system-iformatprovider\))|Converts the value of this instance to an equivalent 64-bit unsigned integer using the specified culture-specific formatting information.|

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
