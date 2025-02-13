---
date_added: 2025-02-11
tags:
  - csharp
---
Up: [csproj file](csproj%20file.md)
___
When project need specific range of libraries you can specify constraints like that:

 ```xml
 <Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net6.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <!-- Minimum -->
    <PackageReference Include="Newtonsoft.Json" Version="13.0.1" />

    <!-- Minimum version -->
    <PackageReference Include="Serilog" Version="2.*" />

    <!-- Version range (inclusive) -->
    <PackageReference Include="NUnit" Version="[3.12.0, 3.13.0]" />

    <!-- Version range (exclusive) -->
    <PackageReference Include="Moq" Version="(4.10.0, 4.15.0)" />

    <!-- Floating patch version -->
    <PackageReference Include="Dapper" Version="2.0.*" />

    <!-- Floating minor version -->
    <PackageReference Include="AutoMapper" Version="10.*" />
  </ItemGroup>

</Project>
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
