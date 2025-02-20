---
date_added: 2025-02-20
tags:
  - csharp
---
Up: [proto file](proto%20file.md)
___
Using [Nuget package](Nuget%20package.md) Grpc tools in [csproj file](csproj%20file.md) generation is happening during [Compilation process](Compilation%20process.md) if protobuf is specified:

  ```csharp
<ItemGroup>
  <Protobuf Update="Proto\DocxSegmentsProcessorTemplate.proto">
    <GrpcServices>Both</GrpcServices>
    <Access>Public</Access> <!-- Optional, only if you need public access -->
  </Protobuf>
</ItemGroup>

or 

<ItemGroup>
  <Protobuf Include="Protos\greet.proto" GrpcServices="Server" />
</ItemGroup>

 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
