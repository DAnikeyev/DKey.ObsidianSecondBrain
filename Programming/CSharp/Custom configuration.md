---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Application configuration](Application%20configuration.md)
___
 You can specify custom configuration flag in [csproj file](csproj%20file.md):
 ```cs
 <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Staging|AnyCPU'">
  <OutputPath>bin\Staging\</OutputPath>
  <DefineConstants>STAGING</DefineConstants>
  <Optimize>true</Optimize>
  <DebugType>pdbonly</DebugType>
</PropertyGroup>
```

and use it like this:
```cs
#if DEBUG
    Console.WriteLine("Debug mode");
#elif STAGING
    Console.WriteLine("Staging mode");
#else
    Console.WriteLine("Release mode");
#endif
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
