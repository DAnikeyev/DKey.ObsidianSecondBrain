---
date_added: 2025-01-09
tags:
  - csharp
---
Up: [CSharp Project](CSharp%20Project.md)
___
 [[XML]] file that contains information about the project. 
  
# Example 
 ```XML
 <Project Sdk="Microsoft.NET.Sdk">  
  
    <PropertyGroup>        
	    <OutputType>Exe</OutputType>  
        <TargetFramework>net8.0</TargetFramework>  
        <ImplicitUsings>enable</ImplicitUsings>  
        <Nullable>enable</Nullable>  
        <RunArguments>D:\Data</RunArguments>  
    </PropertyGroup>  
    <ItemGroup>
          <PackageReference Include="DocumentFormat.OpenXml"Version="3.2.0" />  
      <PackageReference Include="NLog" Version="5.3.4" />  
    </ItemGroup>  
</Project>
```

# References
 1. https://learn.microsoft.com/en-us/dotnet/core/project-sdk/msbuild-props
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
