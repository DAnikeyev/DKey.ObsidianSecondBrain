---
date_added: 2025-02-13
tags:
  - csharp
---
Up: [command dotnet nuget](command%20dotnet%20nuget.md)
___
 The `dotnet nuget verify` command verifies a signed NuGet package.
 
 You can [sign a NuGet package](https://learn.microsoft.com/en-us/nuget/create-packages/sign-a-package) to enable package consumers to validate the package's authenticity and integrity. If verification is enabled, .NET verifies signed packages during a package restore operation, which occurs automatically when a package consumer builds or runs their project.

NuGet package signatures are based on X.509 certificates, and a prerequisite for signed-package verification is a certificate root store that is valid for both code signing and timestamping.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
