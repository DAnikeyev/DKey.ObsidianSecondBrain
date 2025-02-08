---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Project dependency](Project%20dependency.md)
___
 To reference a [[Com component]], use the `<COMReference>` element:
 ```cs
 <ItemGroup>
  <COMReference Include="SomeCOMComponent">
    <Guid>{00000000-0000-0000-0000-000000000000}</Guid>
    <VersionMajor>1</VersionMajor>
    <VersionMinor>0</VersionMinor>
    <Lcid>0</Lcid>
    <WrapperTool>tlbimp</WrapperTool>
  </COMReference>
</ItemGroup>
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
