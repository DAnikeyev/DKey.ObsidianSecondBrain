---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Project reference](Project%20reference.md)
___
 If any file is needed in output directory it has to be specified as a `<Content>` element
 ```cs
 <ItemGroup>
  <Content Include="appsettings.json">
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
