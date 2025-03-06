---
date_added: 2025-03-06
tags:
  - csharp
---
Up: [Other CSharp Features](Other%20CSharp%20Features.md)
___
 Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.

## Nullable context
The `#nullable` preprocessor directive sets the _annotations_ and _warning_ flags in the _nullable context_.

```cs
#nullable enable
```

## Conditional compilation

You use four preprocessor directives to control conditional compilation:

- `#if`: Opens a conditional compilation, where code is compiled only if the specified symbol is defined.
- `#elif`: Closes the preceding conditional compilation and opens a new conditional compilation based on if the specified symbol is defined.
- `#else`: Closes the preceding conditional compilation and opens a new conditional compilation if the previous specified symbol isn't defined.
- `#endif`: Closes the preceding conditional compilation.
Attributes:

| Target Frameworks       | Symbols                                                                                                                                                                                      | Additional symbols  <br>(available in .NET 5+ SDKs)                                                                                                                                                                                                                                    | Platform symbols (available only  <br>when you specify an OS-specific TFM)                                                                                                               |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| .NET 5+ (and .NET Core) | `NET`, `NET9_0`, `NET8_0`, `NET7_0`, `NET6_0`, `NET5_0`, `NETCOREAPP`, `NETCOREAPP3_1`, `NETCOREAPP3_0`, `NETCOREAPP2_2`, `NETCOREAPP2_1`, `NETCOREAPP2_0`, `NETCOREAPP1_1`, `NETCOREAPP1_0` | `NET8_0_OR_GREATER`, `NET7_0_OR_GREATER`, `NET6_0_OR_GREATER`, `NET5_0_OR_GREATER`, `NETCOREAPP3_1_OR_GREATER`, `NETCOREAPP3_0_OR_GREATER`, `NETCOREAPP2_2_OR_GREATER`, `NETCOREAPP2_1_OR_GREATER`, `NETCOREAPP2_0_OR_GREATER`, `NETCOREAPP1_1_OR_GREATER`, `NETCOREAPP1_0_OR_GREATER` | `ANDROID`, `BROWSER`, `IOS`, `MACCATALYST`, `MACOS`, `TVOS`, `WINDOWS`,  <br>`[OS][version]` (for example `IOS15_1`),  <br>`[OS][version]_OR_GREATER` (for example `IOS15_1_OR_GREATER`) |

>[!Info]
> Also supports [Custom configuration](Custom%20configuration.md)

#### Usage
```cs
#if NET40
        WebClient _client = new WebClient();
#else
        HttpClient _client = new HttpClient();
#endif
```

## Define
You use the following two preprocessor directives to define or undefine symbols for conditional compilation:
```cs
#define VERBOSE

#if VERBOSE
   Console.WriteLine("Verbose output version");
#endif
```

## Region
- `#region`: Start a region.
- `#endregion`: End a region.

# Information and errors
- `#error`: Generate a compiler error with a specified message.
- `#warning`: Generate a compiler warning, with a specific message.
- `#line`: Change the line number printed with compiler messages.
## Pragma

- [`#pragma warning`](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/preprocessor-directives#pragma-warning): Enable or disable warnings.
- [`#pragma checksum`](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/preprocessor-directives#pragma-checksum): Generate a checksum.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
