---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Project reference](Project%20reference.md)
___
 For native libraries, you typically use [P-Invoke](P-Invoke.md) in your code, but you can specify the library path using `<Content>` or `<None>` if you need to include it in your build output:
 ```cs
 <ItemGroup>
  <Content Include="native\mylib.dll">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </Content>
</ItemGroup>
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
